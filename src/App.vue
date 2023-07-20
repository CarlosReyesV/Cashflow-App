<template>
  <Suspense>
    <template #default>
      <Home />
    </template>
    <template #fallback>
      <splashScreen></splashScreen>
    </template>
  </Suspense>
</template>

<script>
import splashScreen from "./components/splashScreen.vue";
import { defineAsyncComponent } from "vue";

export default {
  components: {
    splashScreen,
    Home: defineAsyncComponent(
      () =>
        new Promise((resolve) => {
          setTimeout(() => {
            resolve(import("./components/homeP.vue"));
          }, 2500);
        })
    ),
  },
};
</script>

<style>
html,
body,
.app {
  background-color: #bc9576;
  min-height: 100vh;
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
  zoom: 100%;
}
* {
  --brand-black: black;
  --brand-white: white;
  --brand-dgray: #737373;
  --brand-red: rgb(206, 0, 0);
}
</style>
