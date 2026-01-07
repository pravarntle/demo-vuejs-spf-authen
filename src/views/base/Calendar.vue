<template>
  <DocsComponents href="components/calendar.html" />
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Calendar</strong> <small>Days</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Select specific days using the Vue Calendar component. The example below shows basic usage.
      </p>
      <DocsExample href="components/calendar.html#days">
        <div class="d-flex justify-content-center">
          <CCalendar class="bg-body border rounded" locale="en-US" startDate="2024/02/13" />
        </div>
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Calendar</strong> <small>Weeks</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Set the <code>selectionType</code> to <code>week</code> to enable selection of entire week.
        You can also add <code>showWeekNumber</code> to show week numbers.
      </p>
      <DocsExample href="components/calendar.html#weeks">
        <div class="d-flex justify-content-center">
          <CCalendar
            class="bg-body border rounded"
            locale="en-US"
            selectionType="week"
            showWeekNumber
            startDate="2024W15"
          />
        </div>
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Calendar</strong> <small>Months</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Set the <code>selectionType</code> property to <code>month</code> to enable selection of
        entire months.
      </p>
      <DocsExample href="components/calendar.html#months">
        <div class="d-flex justify-content-center">
          <CCalendar
            class="bg-body border rounded"
            locale="en-US"
            selectionType="month"
            startDate="2024-2"
          />
        </div>
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Calendar</strong> <small>Years</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Set the <code>selectionType</code> property to <code>year</code> to enable years range
        selection.
      </p>
      <DocsExample href="components/calendar.html#years">
        <div class="d-flex justify-content-center">
          <CCalendar
            class="bg-body border rounded"
            locale="en-US"
            selectionType="year"
            startDate="2024"
          />
        </div>
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader>
      <strong>Vue Calendar</strong> <small>Multiple calendar panels</small>
    </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Display multiple calendar panels side by side by setting the <code>calendars</code>{' '}
        property. This can be useful for selecting ranges or comparing dates across different
        months.
      </p>
      <DocsExample href="components/calendar.html#multiple-calendar-panels">
        <div class="d-flex justify-content-center">
          <CCalendar :calendars="2" class="bg-body border rounded" locale="en-US" />
        </div>
      </DocsExample>
    </CCardBody>
  </CCard>
  <CCard class="mb-4">
    <CCardHeader> <strong>Vue Calendar</strong> <small>Range selection</small> </CCardHeader>
    <CCardBody>
      <p class="text-body-secondary small">
        Enable range selection to allow users to pick a start and end date. This example shows how
        to configure the Vue Calendar component to handle date ranges.
      </p>
      <DocsExample href="components/calendar.html#range-selection">
        <div class="d-flex justify-content-center">
          <CCalendar
            :calendars="2"
            class="bg-body border rounded"
            locale="en-US"
            range
            startDate="2022/08/23"
            endDate="2022/09/08"
          />
        </div>
      </DocsExample>
    </CCardBody>
  </CCard>
</template>
