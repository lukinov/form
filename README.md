![Formengine](./readme-assets/Formengine_bigpicture_2.png)

<!-- ==================== FORMENGINE CORE BADGES ==================== -->
[![Give us a Star](https://img.shields.io/badge/⭐️_Give_us_a_star-FF69B4?style=for-the-badge)](https://github.com/optimajet/formengine/stargazers)
[![npm](https://img.shields.io/npm/v/@react-form-builder/core?style=for-the-badge&logo=npm&color=4286F4)](https://www.npmjs.com/package/@react-form-builder/core)
[![Total Downloads](https://img.shields.io/npm/dt/@react-form-builder/core?style=for-the-badge&logo=npm&color=4286F4)](https://www.npmjs.com/package/@react-form-builder/core)
[![License MIT](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](https://github.com/optimajet/formengine/blob/master/LICENSE)
[![Contributions welcome](https://img.shields.io/badge/Contribute-💡_Ideas-FF69B4?style=for-the-badge&logo=github)](https://github.com/optimajet/formengine/issues)
[![Join Community](https://img.shields.io/badge/💬_Join-Community-4286F4?style=for-the-badge&logo=github)](https://github.com/optimajet/formengine/discussions)
<!-- ================================================================ -->

## 📦 Installation  

Install the core package and RSuite free form components:  
 ```bash  
 npm install @react-form-builder/core @react-form-builder/components-rsuite  
 ```  
## 🚀 Quick Start Example

Here's a minimal example of a **React Form Engine Core** form using RSuite components:

```tsx
import { viewWithCss } from '@react-form-builder/components-rsuite'
import { buildForm, FormViewer } from '@react-form-builder/core'

const simpleForm = buildForm({ errorType: 'RsErrorMessage' })
  .component('container', 'RsContainer')
  .style({ flexDirection: 'row' })
  .children((builder) =>
    builder
      .component('firstName', 'RsInput')
      .prop('placeholder', 'Enter your first name')
      .prop('label', 'First Name')
      .validation('required')

      .component('lastName', 'RsInput')
      .prop('placeholder', 'Enter your last name')
      .prop('label', 'Last Name')
      .validation('required')
  )

  .component('birthDate', 'RsDatePicker')
  .prop('label', 'Birth Date')
  .prop('oneTap', true)
  .validation('min')
  .args({ value: '1900-01-07T12:25:37.000Z' })

  .component('submit', 'RsButton')
  .prop('children', 'Submit')
  .prop('color', 'blue')
  .prop('appearance', 'primary')
  .event('onClick')
  .commonAction('validate')
  .args({ failOnError: true })
  .customAction('onSubmit')
  .json()

export const App = () => {
  return (
    <FormViewer
      view={viewWithCss}
      getForm={() => simpleForm}
      actions={{
        onSubmit: (e) => {
          // submit the form to the backend
          alert('Form data: ' + JSON.stringify(e.data))
        },
      }}
    />
  )
}
