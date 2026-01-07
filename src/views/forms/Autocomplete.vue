<template>
  <CRow>
    <CCol :xs="12">
      <DocsComponents href="forms/autocomplete.html" />
      <CCard class="mb-4">
        <CCardHeader>
          <strong>CoreUI Autocomplete</strong> <small>Basic example</small>
          <ProBadge />
        </CCardHeader>
        <CCardBody>
          <p class="text-body-secondary small">
            A straightforward demonstration of how to implement a basic Vue.js Autocomplete
            input field, highlighting essential attributes and configurations.
          </p>
          <DocsExample href="forms/autocomplete.html#basic-example">
            <CAutocomplete
              id="autocomplete1"
              label="Programming Languages"
              :options="programmingLanguages"
              placeholder="Type to search...."
              cleaner
              highlight-options-on-search
              indicator
              search-no-results-label="No results found"
              show-hints
              value="React.js"
            />
          </DocsExample>
        </CCardBody>
      </CCard>
    </CCol>

    <CCol :xs="12">
      <CCard class="mb-4">
        <CCardHeader>
          <strong>CoreUI Autocomplete</strong> <small>With hints</small>
          <ProBadge />
        </CCardHeader>
        <CCardBody>
          <p class="text-body-secondary small">
            Enable hints by adding <code>show-hints</code> to show completion
            suggestions as you type.
          </p>
          <DocsExample href="forms/autocomplete.html#show-hints">
            <CAutocomplete
              id="autocomplete2"
              label="Frameworks"
              :options="frameworks"
              placeholder="Search frameworks..."
              show-hints
            />
          </DocsExample>
        </CCardBody>
      </CCard>
    </CCol>

    <CCol :xs="12">
      <CCard class="mb-4">
        <CCardHeader>
          <strong>CoreUI Autocomplete</strong> <small>With cleaner button</small>
          <ProBadge />
        </CCardHeader>
        <CCardBody>
          <p class="text-body-secondary small">
            Add a clear button by setting <code>cleaner</code>.
          </p>
          <DocsExample href="forms/autocomplete.html#cleaner-functionality">
            <CAutocomplete
              id="autocomplete3"
              label="Countries"
              :options="countries"
              placeholder="Select country..."
              cleaner
            />
          </DocsExample>
        </CCardBody>
      </CCard>
    </CCol>

    <CCol :xs="12">
      <CCard class="mb-4">
        <CCardHeader>
          <strong>CoreUI Autocomplete</strong> <small>Highlight matching text</small>
          <ProBadge />
        </CCardHeader>
        <CCardBody>
          <p class="text-body-secondary small">
            Enable text highlighting in dropdown options with
            <code>highlight-options-on-search</code>.
          </p>
          <DocsExample href="forms/autocomplete.html#highlight-matching-text">
            <CAutocomplete
              id="autocomplete4"
              label="Cities"
              :options="cities"
              placeholder="Find city..."
              highlight-options-on-search
            />
          </DocsExample>
        </CCardBody>
      </CCard>
    </CCol>

    <CCol :xs="12">
      <CCard class="mb-4">
        <CCardHeader>
          <strong>CoreUI Autocomplete</strong> <small>Multiple configurations</small>
          <ProBadge />
        </CCardHeader>
        <CCardBody>
          <p class="text-body-secondary small">
            Combine multiple features for enhanced functionality.
          </p>
          <DocsExample href="forms/autocomplete.html">
            <CForm>
              <CRow>
                <CCol :md="6" class="mb-3">
                  <CAutocomplete
                    id="autocomplete6"
                    label="Technologies (with hints & cleaner)"
                    :options="technologies"
                    placeholder="Choose technology..."
                    show-hints
                    cleaner
                    highlight-options-on-search
                  />
                </CCol>
                <CCol :md="6" class="mb-3">
                  <CAutocomplete
                    id="autocomplete7"
                    label="Colors"
                    :options="colors"
                    placeholder="Pick a color..."
                    cleaner
                  />
                </CCol>
              </CRow>
            </CForm>
          </DocsExample>
        </CCardBody>
      </CCard>
    </CCol>

    <CCol :xs="12">
      <CCard class="mb-4">
        <CCardHeader>
          <strong>CoreUI Autocomplete</strong> <small>Validation states</small>
          <ProBadge />
        </CCardHeader>
        <CCardBody>
          <p class="text-body-secondary small">
            Apply validation states using Bootstrap's validation classes.
          </p>
          <DocsExample href="forms/autocomplete.html#validation-states">
            <CForm>
              <CRow>
                <CCol :md="4" class="mb-3">
                  <CAutocomplete
                    id="autocomplete-valid"
                    label="Valid input"
                    :options="basicOptions"
                    placeholder="Valid state..."
                    valid
                    feedback-valid="Valid choice!"
                  />
                </CCol>
                <CCol :md="4" class="mb-3">
                  <CAutocomplete
                    id="autocomplete-invalid"
                    label="Invalid input"
                    :options="basicOptions"
                    placeholder="Invalid state..."
                    invalid
                    feedback-invalid="Please select a valid option."
                  />
                </CCol>
                <CCol :md="4" class="mb-3">
                  <CAutocomplete
                    id="autocomplete-disabled"
                    label="Disabled"
                    :options="basicOptions"
                    placeholder="Disabled state..."
                    disabled
                  />
                </CCol>
              </CRow>
            </CForm>
          </DocsExample>
        </CCardBody>
      </CCard>
    </CCol>
  </CRow>
</template>

<script setup>
const programmingLanguages = [
  'JavaScript',
  'TypeScript',
  'Python',
  'Java',
  'C#',
  'C++',
  'Go',
  'Rust',
  'Swift',
  'Kotlin',
  'React.js',
]

const frameworks = [
  'Angular',
  'Bootstrap',
  'React.js',
  'Vue.js',
  'Svelte',
  'Next.js',
  'Nuxt.js',
  'jQuery',
]

const countries = [
  'United States',
  'Canada',
  'United Kingdom',
  'Germany',
  'France',
  'Italy',
  'Spain',
  'Poland',
  'Netherlands',
  'Belgium',
]

const cities = [
  'New York',
  'Los Angeles',
  'Chicago',
  'Houston',
  'Phoenix',
  'Philadelphia',
  'San Antonio',
  'San Diego',
  'Dallas',
  'San Jose',
]

const technologies = [
  'HTML',
  'CSS',
  'JavaScript',
  'TypeScript',
  'React',
  'Vue.js',
  'Angular',
  'Node.js',
  'Express',
  'MongoDB',
  'PostgreSQL',
  'Redis',
]

const colors = [
  'Red',
  'Green',
  'Blue',
  'Yellow',
  'Orange',
  'Purple',
  'Pink',
  'Cyan',
  'Magenta',
  'Lime',
]

const basicOptions = ['Option 1', 'Option 2', 'Option 3', 'Option 4']
</script>