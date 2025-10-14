![Formengine](./readme-assets/Formengine_bigpicture_2.png)

<!-- ==================== FORMENGINE CORE BADGES ==================== -->
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

 ```
## ✨ Formengine Core Key Features

- 🧩 **UI-Agnostic Components** — Works seamlessly with any UI library (MUI, Ant Design, shadcn/ui, and others).  
- ⚡ **Pre-Built RSuite Integration** — Includes a ready-to-use component library: `@react-form-builder/components-rsuite`.  
- 🧠 **Framework Support**
  - **Next.js Integration** — Works out of the box with Next.js.  
  - **Remix Compatibility** — Fully supports Remix.  
  - **Framework-Agnostic** — Can also be used without any framework via CDN.  
- 🗄️ **Multi-Database Support** — Compatible with MySQL, PostgreSQL, MongoDB, SQLite, and more.  
- ✅ **Built-in Validation with Zod** — Pre-configured validation powered by Zod.  
- 🔧 **Extensible Validation Support** — Works with Yup, AJV, Zod, Superstruct, Joi, and other libraries.  
- 📱 **Responsive Layouts** — Build forms that automatically adapt to all screen sizes.  
- ⚙️ **Custom Actions** — Enhance forms with interactive logic through custom JavaScript.  
- 🔄 **Dynamic Properties** — Enable real-time component updates with MobX-powered reactivity.  
- 💾 **Flexible Storage Options**
  - Store complete form definitions as JSON.  
  - Programmatically generate forms via code.
  
 ## Drag and Drop Premium Formbuilder 

 ![Formengine Drag and n Drop](./readme-assets/DND-react-form-builder.png)

 ![Formengine Drag and n Drop](./readme-assets/dndfb.gif)
