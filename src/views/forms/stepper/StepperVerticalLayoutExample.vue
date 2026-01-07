<script setup>
import { ref, useId } from 'vue'

const stepperRef = ref()
const currentStep = ref(1)
const finish = ref(false)
const uid = useId()

const steps = ['Step 1', 'Step 2', 'Step 3']
</script>

<template>
  <div>
    <CStepper
      :steps="steps"
      layout="vertical"
      @finish="finish = true"
      @reset="finish = false"
      @step-change="(step) => (currentStep = step)"
      ref="stepperRef"
    >
      <template #step-1="{ formRef }">
        <form class="row g-3 py-3" novalidate :ref="formRef">
          <CCol :md="4">
            <CFormInput type="text" value="Łukasz" label="First name" />
          </CCol>
          <CCol :md="4">
            <CFormInput type="text" value="Holeczek" label="Last name" />
          </CCol>
          <CCol :md="4">
            <CFormLabel :for="`validationCustomUsername-${uid}-01`">Username</CFormLabel>
            <CInputGroup>
              <CInputGroupText :id="`inputGroupPrependFeedback-${uid}`">@</CInputGroupText>
              <CFormInput
                type="text"
                :id="`validationCustomUsername-${uid}-01`"
                :aria-describedby="`inputGroupPrependFeedback-${uid}`"
              />
            </CInputGroup>
          </CCol>
        </form>
      </template>

      <template #step-2="{ formRef }">
        <form class="row g-3 py-3" novalidate :ref="formRef">
          <CCol :md="6">
            <CFormInput type="text" label="City" />
          </CCol>
          <CCol :md="3">
            <CFormSelect label="State">
              <option disabled>Choose...</option>
              <option>...</option>
            </CFormSelect>
          </CCol>
          <CCol :md="3">
            <CFormInput type="text" label="Zip" />
          </CCol>
        </form>
      </template>

      <template #step-3="{ formRef }">
        <form class="row g-3 pt-3" novalidate :ref="formRef">
          <CCol :md="6">
            <CFormInput type="email" label="Email" />
          </CCol>
          <CCol :md="6">
            <CPasswordInput label="Password" />
          </CCol>
          <CCol :xs="12">
            <CFormCheck type="checkbox" label="Agree to terms and conditions" />
          </CCol>
        </form>
      </template>
    </CStepper>
    <div v-if="finish">All steps are complete—you're finished.</div>

    <div class="d-flex gap-2 mt-4">
      <CButton v-if="!finish && currentStep > 1" color="secondary" @click="stepperRef?.prev()">
        Previous
      </CButton>
      <CButton
        v-if="!finish && currentStep < steps.length"
        color="primary"
        @click="stepperRef?.next()"
      >
        Next
      </CButton>
      <CButton
        v-if="!finish && currentStep === steps.length"
        color="primary"
        @click="stepperRef?.finish()"
      >
        Finish
      </CButton>
      <CButton v-if="finish" color="danger" @click="stepperRef?.reset()"> Reset </CButton>
    </div>
  </div>
</template>
