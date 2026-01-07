# How to install
1. รันคำสั่ง 

```
git clone https://github.com/pravarntle/demo-vuejs-spf-authen.git demo-app
```

2. เข้าไปยังโฟลเดอร์ด้วยคำสั่ง cd demo-app
3. รันคำสั่ง npm install เพื่อติดตั้ง packages
4. เมื่อติดตั้งเสร็จให้ทดสอบโดยรันคำสั่ง npm run dev จากนั้นเปิด browser พิมพ์ URL http://localhost:3000 เพื่อดูผลลัพธ์

# ทดสอบการทำงาน SSO ร่วมกับ SPF Step-by-Step
ขั้นตอนที่ 1 : สร้าง Web Page สำหรับรองรับการทดสอบ Re-Direct
1. สร้างไฟล์ใหม่ภายใต้ Project > src > views ตั้งชื่อไฟล์ว่า SSOLogin.vue
2. ใส่ Code HTML หรือ Copy จากข้อความด้านล่าง

```
<template>
  <CRow>
    <CCol>
      <h4>HELLO WORLD</h4>
    </CCol>
  </CRow>
</template>
```

3. เพิ่ม Router เพื่อชี้มาที่ Page นี้ โดยเปิดไฟล์ที่ Path : Project > src > router > index.js แล้วเพิ่ม Code ด้านล่างเข้าไป

```
{
    path: '/login/sso',
    name: 'SSO Login',
    component: () => import('@/views/SSOLogin.vue'),
}
```

4. ทดสอบเรียกหน้าเว็บโดยการพิมพ์ URL ไปที่ http://localhost:3000/login/sso

ขั้นตอนที่ 2 : เขียนฟังก์ชันเพื่อเช็ค Session Cookie
1. ติดตั้ง Package axios เพื่อเติม โดยให้ Stop server ที่ทำงานอยู่ก่อน แล้วรันคำสั่ง

```
npm install axios
```

2. เขียนฟังก์ชันเพื่อ Verify Cookie ที่ได้รับไปยัง Kong API โดยให้สร้างโฟลเดอร์และไฟล์ใหม่ใน Path : Project > src > helpers > authHelper.js โดยใช้ Code ด้านล่างนี้

```
import axios from "axios";
const GATEWAY_URL = 'https://api-uat.exat.co.th/'

export async function AUTH_SSO() {
  try {
    axios.defaults.withCredentials = true;
    const res = await axios.get(
      `${GATEWAY_URL}sso/session`,
      { withCredentials: true },
    );

    const user_data = {
      username: res.data.username,
      displayName: res.data.attributes.displayName,
      accountExpires: res.data.attributes.accountExpires,
      email: res.data.attributes.email || "",
    };
    return res;
  } catch (error) {
    return error;
  }
}
```

ขั้นตอนที่ 3 : เรียกใช้ฟังก์ชันเพื่อ Verify Cookie ใน Web Page ที่เตรียมไว้
1. กลับไปที่ไฟล์ SSOLogin.vue ที่สร้างไว้ในขั้นตอนแรก
2. ทำการ import authHelper.js มาใช้ โดยเพื่ม Code ด้านล่างเข้าไป

```
<script setup>
import { AUTH_SSO } from '../helpers/authHelper';
</script>
```

3. จากนั้นทดสอบให้เรียกฟังก์ชันดังกล่าวในขณะที่ Web Page มีการถูกเรียกใช้งาน แล้ว Logs ดูผลลัพธ์ โดยเพิ่ม Code

```
import { ref, onMounted } from 'vue';

onMounted(async () => {
  try {
    const sso = await AUTH_SSO();
    console.log(sso)
  } catch (error) {
    console.log("error", error);
  }
});
```