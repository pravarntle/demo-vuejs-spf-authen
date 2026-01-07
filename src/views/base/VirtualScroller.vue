<template>
  <DocsComponents href="components/virtual-scroller.html" />
  <CCard>
    <CCardHeader> <strong>Virtual Scroller</strong> <small>(10000 Items)</small></CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Virtual scrollers work by only rendering the items that are currently visible on the screen,
        and as the user scrolls through the list, new items are dynamically loaded and added to the
        view. This helps to reduce the amount of data that needs to be loaded and processed at any
        given time, which can improve the performance and responsiveness of the UI.
      </p>
      <DocsExample href="components/virtual-scroller.html#virtual-scroll-10000-items">
        <div class="bg-body border p-3 rounded">
          <CVirtualScroller :visibleItems="20">
            <div v-for="(item, index) in 10000" :key="index">Option {{ item }}</div>
          </CVirtualScroller>
        </div>
      </DocsExample>
    </CCardBody>
  </CCard>
</template>
