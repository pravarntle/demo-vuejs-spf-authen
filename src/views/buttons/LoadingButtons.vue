<script setup lang="ts">
const buttonColors = ['primary', 'secondary', 'success', 'danger', 'warning', 'info']
</script>

<template>
  <DocsComponents href="components/loading-button.html" />
  <CCard class="mb-4">
    <CCardHeader>
      <strong>Vue Loading Button</strong>
    </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        CoreUI includes buttons with built-in loading indicators. Indicate the loading state of the
        button bridging the gap between action and feedback.
      </p>
      <DocsExample href="components/loading-button.html">
        <CRow class="py-4 text-center">
          <CCol v-for="(color, index) in buttonColors" :key="index" md="2">
            <CLoadingButton :color="color" :timeout="2000"> Submit </CLoadingButton>
          </CCol>
        </CRow>
        <CRow class="py-4 text-center">
          <CCol v-for="(color, index) in buttonColors" :key="index" md="2">
            <CLoadingButton :color="color" variant="outline" :timeout="2000">
              Submit
            </CLoadingButton>
          </CCol>
        </CRow>
        <CRow class="py-4 text-center">
          <CCol v-for="(color, index) in buttonColors" :key="index" md="2">
            <CLoadingButton :color="color" variant="ghost" :timeout="2000"> Submit </CLoadingButton>
          </CCol>
        </CRow>
      </DocsExample>
      <h4 class="mt-5">Loading Buttons with grow spinner</h4>
      <DocsExample href="components/loading-button.html#grow">
        <CRow class="py-4 text-center">
          <CCol v-for="(color, index) in buttonColors" :key="index" md="2">
            <CLoadingButton :color="color" spinner-type="grow" :timeout="2000">
              Submit
            </CLoadingButton>
          </CCol>
        </CRow>
        <CRow class="py-4 text-center">
          <CCol v-for="(color, index) in buttonColors" :key="index" md="2">
            <CLoadingButton :color="color" spinner-type="grow" variant="outline" :timeout="2000">
              Submit
            </CLoadingButton>
          </CCol>
        </CRow>
        <CRow class="py-4 text-center">
          <CCol v-for="(color, index) in buttonColors" :key="index" md="2">
            <CLoadingButton :color="color" spinner-type="grow" variant="ghost" :timeout="2000">
              Submit
            </CLoadingButton>
          </CCol>
        </CRow>
      </DocsExample>
    </CCardBody>
  </CCard>
</template>
