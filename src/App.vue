<template>
  <q-layout
    view="lHh Lpr lFf"><!--Quasar layout component (<q-layout>) with a view property set to "lHh Lpr lFf", which specifies a horizontal layout with a header, a footer, and a left-side drawer.-->
    <q-page-container> <!-- component that wraps the main content of the page-->
      <CRUDApp />
      <!--This component includes the child component which is another custom component defined in the application.-->
    </q-page-container>
  </q-layout>
</template>








<script>
/* section contains the JavaScript code for the component */
import { ref } from 'vue'
import CRUDApp from '../src/components/CRUDApp.vue'

/* This code is defining a Vue.js single-file component and exporting it as the default export. 
The component is named "LayoutDefault" and it includes a child component called "CRUDApp".*/
export default {
  /*   The "name" property is used to give the component a name that can be used for debugging and in Vue.js DevTools. 
  In this case, the name is "LayoutDefault".*/
  name: 'LayoutDefault',

/*   The "components" property is used to register child components that can be used within the template of the parent component.
 In this case, the "CRUDApp" component is registered as a child component of the "LayoutDefault" component. 
 This means that the "CRUDApp" component can be used in the template of the "LayoutDefault" component like this: <CRUDApp/>.
 */
/*  By including the child component as a registered component, 
it makes it possible to use the component within the template of the parent component without needing to 
import it in each component file where it is used. 
It simplifies the component hierarchy and makes it easier to manage the components as the application grows. 
 */
components: {
    CRUDApp
  },



/*This code is defining the setup function of the Vue.js component.
The setup function is a new feature in Vue.js 3 that allows you to set up the component's reactive data and functions.
It runs before the component is mounted, and it is used to set up the reactive data and functions that the component needs.
In this case, the setup function is using the ref function from the Vue library to create a reactive variable called leftDrawerOpen. 
The ref function is used to create reactive variables in Vue.js that can be updated and watched for changes.
The leftDrawerOpen variable is initialized to false, which means that the left-side drawer in the component is initially closed. 
Because the leftDrawerOpen variable is reactive, any changes to its value will cause the component to update and re-render.
By returning an object that contains the leftDrawerOpen variable from the setup function,
the variable becomes available for use within the template and methods of the component. 
For example, it can be used to conditionally show or hide the left-side drawer based on its value.
 */
  setup() {
    return {
      leftDrawerOpen: ref(false)
    }
  }
}
</script>
