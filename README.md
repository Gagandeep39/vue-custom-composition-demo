# Vue Custom Composition Demo

- [Vue Custom Composition Demo](#vue-custom-composition-demo)
  - [Deployment](#deployment)
  - [Csutom composition](#csutom-composition)
  - [NOTE](#note)

## Deployment

- Checkout Deployment at <https://gagandeep39.github.io/vue-custom-composition-demo/>

## Csutom composition

- It refers to reusable functions in Composition API
- Usually stored in directly named `hooks`, `custom-composable-functions`, `composables`
- Naming convection `useFunctioName`

```js
// Custom Composition
import { ref } from 'vue';
const useAlert = () => {
  const alertIsVisible = ref(false);

  function showAlert() {
    alertIsVisible.value = true;
  }
  function hideAlert() {
    alertIsVisible.value = false;
  }

  return [alertIsVisible, showAlert, hideAlert];
};
export default useAlert;
```

```js
// Using the Custom compositon
setup() {
    const [alertIsVisible, showAlert, hideAlert] = useAlert();
    return {
      alertIsVisible,
      showAlert,
      hideAlert,
    };
  },
```

## NOTE

- **Mixins** works with Options API
- **Custom Composition** works with Composition API
