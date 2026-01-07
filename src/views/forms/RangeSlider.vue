<template>
  <DocsComponents href="forms/range-slider.html" />
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Range Slider</strong> <small></small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        The <strong>Vue Range Slider</strong> component allows users to select a value or range of
        values within a predefined range. Unlike the standard{' '}
        <code>&lt;input type="range"&gt;</code>, the Range Slider offers enhanced customization
        options, including multiple handles, labels, tooltips, and vertical orientation. It ensures
        consistent styling across browsers and provides a rich set of features for advanced use
        cases.
      </p>
      <DocsExample href="forms/range-slider.html#overview" tabContentClass="bg-opacity-10">
        <CRangeSlider :value="[25, 75]" :labels="['Low', 'Medium', 'High']" />
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Range Slider</strong> <small>Multiple handles</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Enable multiple handles to allow the selection of a range or/and multiple values.
      </p>
      <DocsExample href="forms/range-slider.html#multiple-handles" tabContentClass="bg-opacity-10">
        <CRangeSlider class="mb-3" :value="[20, 40]" />
        <CRangeSlider class="mb-3" :value="[20, 40, 60]" />
        <CRangeSlider :value="[20, 40, 60, 80]" />
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader>
      <strong>Vue Range Slider</strong> <small>Vertical Range Slider</small>
    </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">Rotate the slider to a vertical orientation.</p>
      <DocsExample href="forms/range-slider.html#multiple-handles" tabContentClass="bg-opacity-10">
        <div class="d-flex">
          <CRangeSlider class="me-3" :value="20" vertical />
          <CRangeSlider class="me-3" :value="[20, 80]" vertical />
          <CRangeSlider :value="[20, 80, 100]" vertical />
        </div>
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Range Slider</strong> <small>Disabled</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">Disable the slider to prevent user interaction.</p>
      <DocsExample href="forms/range-slider.html#disabled" tabContentClass="bg-opacity-10">
        <CRangeSlider class="mb-3" :value="50" disabled />
        <CRangeSlider :value="[50, 75]" disabled />
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Range Slider</strong> <small>Min and max</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Vue Range Slider component has implicit values for <code>min</code> and{' '}
        <code>max</code>—<code>0</code> and <code>100</code>, respectively. You may specify new
        values for those using the <code>min</code> and <code>max</code> attributes.
      </p>
      <DocsExample href="forms/range-slider.html#min-and-max" tabContentClass="bg-opacity-10">
        <CRangeSlider class="mb-3" :min="-50" :max="150" :value="50" />
        <CRangeSlider :min="-50" :max="150" :value="[50, 75]" />
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Range Slider</strong> <small>Distance</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Sets the minimum distance between multiple slider handles by setting{' '}
        <code>distance</code> and ensures that the handles do not overlap or get too close.
      </p>
      <DocsExample href="forms/range-slider.html#distance" tabContentClass="bg-opacity-10">
        <CRangeSlider :distance="10" :value="[50, 75]" />
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Range Slider</strong> <small>Labels</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Add labels to specific points on the slider for better context. If you provide an array of
        strings, as in the example below, then labels will be spaced at equal distances from the
        beginning to the end of the slider.
      </p>
      <DocsExample href="forms/range-slider.html#labels" tabContentClass="bg-opacity-10">
        <CRangeSlider :labels="['Start', 'Middle', 'End']" :value="[30, 70]" />
      </DocsExample>
    </CCardBody>
  </CCard>
</template>
