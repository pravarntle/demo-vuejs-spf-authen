<script setup>
import {
  cilHeart,
  cilMoodVeryBad,
  cilMoodBad,
  cilMoodGood,
  cilMoodVeryGood,
  cilMeh,
} from '@coreui/icons'

const icons = {
  1: { icon: cilMoodVeryBad, customClassName: ' ' },
  2: { icon: cilMoodBad, customClassName: ' ' },
  3: { icon: cilMeh, customClassName: ' ' },
  4: { icon: cilMoodGood, customClassName: ' ' },
  5: { icon: cilMoodVeryGood, customClassName: ' ' },
}

const activeIcons = {
  1: { icon: cilMoodVeryBad, customClassName: 'text-danger-emphasis' },
  2: { icon: cilMoodBad, customClassName: 'text-danger' },
  3: { icon: cilMeh, customClassName: 'text-warning' },
  4: { icon: cilMoodGood, customClassName: 'text-success' },
  5: { icon: cilMoodVeryGood, customClassName: 'text-success-emphasis' },
}
</script>
<template>
  <DocsComponents href="forms/rating.html" />
  <CCard class="mb-4">
    <CCardHeader>
      <strong>Vue Rating</strong>
    </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Embed the Rating component in your Vue application like this:
      </p>
      <DocsExample href="forms/rating.html#how-to-use-vue-rating-component">
        <CRating :value="3" />
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Rating</strong> <small>Read only</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Set the Vue rating component to read-only by adding <code>readOnly</code> property. This
        disables interaction, preventing users from changing the displayed rating value.
      </p>
      <DocsExample href="forms/rating.html#read-only">
        <CRating readOnly :value="3" />
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Rating</strong> <small>Disabled</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Add the <code>disabled</code> boolean property to give it a grayed out appearance, remove
        pointer events, and prevent focusing.
      </p>
      <DocsExample href="forms/rating.html#disabled">
        <CRating disabled :value="3" />
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Rating</strong> <small>Tooltips</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Enable descriptive text on hover by adding <code>tooltips</code> prop. This provides
        immediate feedback or guidance as the user interacts with the rating items.
      </p>
      <DocsExample href="forms/rating.html#tooltips">
        <CRating tooltips :value="3" />
      </DocsExample>
      <p class="text-body-secondary small">
        For custom messages, provide an array of labels corresponding to each rating value to
        enhance the user's understanding of each rating level.
      </p>
      <DocsExample href="forms/rating.html#tooltips">
        <CRating :tooltips="['Very bad', 'Bad', 'Meh', 'Good', 'Very good']" :value="3" />
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Rating</strong> <small>Sizes</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Larger or smaller Vue rating component? Add <code>size="lg"</code> or{' '}
        <code>size="sm"</code> for additional sizes.
      </p>
      <DocsExample href="forms/rating.html#sizes">
        <CRating size="sm" :value="3" />
        <CRating :value="3" />
        <CRating size="lg" :value="3" />
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Rating</strong> <small>Precision</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Adjust the granularity of the Rating component by setting <code>precision</code> prop. This
        attribute allows for fractional ratings, such as quarter values, to provide more precise
        feedback.
      </p>
      <DocsExample href="forms/rating.html#precision">
        <CRating :precision="0.25" :value="3" />
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Rating</strong> <small>Number of items</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Control the total number of rating items displayed by using <code>itemCount</code>{' '}
        property. You can create a Vue rating component with a custom scale, be it larger for
        detailed assessments or smaller for simplicity.
      </p>
      <DocsExample href="forms/rating.html#number-of-items">
        <CRating class="mb-3" :itemCount="20" :value="5" />
        <CRating :itemCount="3" :value="1" />
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Rating</strong> <small>Custom icons</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Customize the Vue rating component with your choice of SVG icons by assigning new values
        to the <code>activeIcon</code> and <code>icon</code> properties in the JavaScript options.
        This allows for a unique look tailored to the design language of your site or application.
      </p>
      <DocsExample href="forms/rating.html#custom-icons">
        <CRating :value="3">
          <template #activeIcon>
            <CIcon :icon="cilHeart" customClassName="text-danger" />
          </template>
          <template #icon>
            <CIcon :icon="cilHeart" customClassName=" " />
          </template>
        </CRating>
      </DocsExample>
      <p class="text-body-secondary small">
        For a more dynamic experience, define different icons for each rating value, enhancing the
        visual feedback:
      </p>
      <DocsExample href="forms/rating.html#custom-icons">
        <CRating
          highlightOnlySelected
          :tooltips="['Very bad', 'Bad', 'Meh', 'Good', 'Very good']"
          :value="3"
        >
          <template #icon="{ value }">
            <CIcon :icon="icons[value].icon" :customClassName="icons[value].customClassName" />
          </template>
          <template #activeIcon="{ value }">
            <CIcon
              :icon="activeIcons[value].icon"
              :customClassName="activeIcons[value].customClassName"
            />
          </template>
        </CRating>
      </DocsExample>
    </CCardBody>
  </CCard>
</template>
