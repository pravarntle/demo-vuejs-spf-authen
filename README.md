# How to install
1. รันคำสั่ง git clone https://github.com/pravarntle/demo-vuejs-spf-authen.git demo-app
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

