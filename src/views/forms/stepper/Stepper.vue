<script setup>
import StepperExample from './StepperExample.vue'
import StepperVerticalIndicatorLayoutExample from './StepperVerticalIndicatorLayoutExample.vue'
import StepperVerticalLayoutExample from './StepperVerticalLayoutExample.vue'
</script>

<template>
  <CRow>
    <CCol :xs="12">
      <DocsComponents href="forms/stepper.html" />
      <CCard class="mb-4">
        <CCardHeader>
          <strong>Vue Stepper</strong>
        </CCardHeader>
        <CCardBody>
          <p class="text-body-secondary small">
            The Vue Stepper component helps you build intuitive, multi-step form experiences (Form
            Wizards) for your Vue applications. It supports horizontal and vertical layouts,
            built-in form validation, custom indicators, and seamless integration with any Vue
            form library.
          </p>
          <DocsExample href="forms/stepper.html#example">
            <StepperExample />
          </DocsExample>
        </CCardBody>
      </CCard>
      <CCard class="mb-4">
        <CCardHeader>
          <strong>Vue Stepper</strong> <small>Vertical indicator layout</small>
        </CCardHeader>
        <CCardBody>
          <p class="text-body-secondary small">
            In this example, the step indicators are displayed vertically above the labels using the
            <code>stepButtonLayout="vertical"</code> prop, while the form content remains laid out
            horizontally. This option is useful when you want a more compact and visually balanced
            look for the step navigation, especially in narrower layouts. Use{' '}
            <code>stepButtonLayout="vertical"</code> when you want a clear visual separation of
            steps without changing the main content flow.
          </p>
          <DocsExample href="forms/stepper.html#vertical-indicator-layout">
            <StepperVerticalIndicatorLayoutExample />
          </DocsExample>
        </CCardBody>
      </CCard>
      <CCard class="mb-4">
        <CCardHeader> <strong>Vue Stepper</strong> <small>Vertical layout</small> </CCardHeader>
        <CCardBody>
          <p class="text-body-secondary small">
            This example shows a fully vertical multi-step form wizard created with the Vue
            Stepper component. By using the <code>layout="vertical"</code> prop, both the step
            indicators and the step content are stacked vertically. This layout is ideal for mobile
            devices or designs where vertical flow is preferred. Choose{' '}
            <code>layout="vertical"</code> if you want the entire wizard to guide users in a
            top-to-bottom progression.
          </p>
          <DocsExample href="forms/stepper.html#vertical-layout">
            <StepperVerticalLayoutExample />
          </DocsExample>
        </CCardBody>
      </CCard>
    </CCol>
  </CRow>
</template>
