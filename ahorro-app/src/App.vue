<template>
  <Suspense>
    <template #default>
      <HelloWorld/>
    </template>

    <template #fallback>
      <SplashScreen/>
    </template>
  </Suspense>
</template>

<script>
import SplashScreen from './components/SplashScreen.vue';
import {defineAsyncComponent } from 'vue';

export default {
  name: 'App',
  components: {
    SplashScreen,
    HelloWorld: defineAsyncComponent(() => 
  new Promise((resolve) => {
    setTimeout(() => {
      resolve(import("./components/HelloWorld.vue"))
    },2500);
  })
)
  }
}
</script>

<style>
html,
body,
.app {
  min-height: 100vh;
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}
* {
  --brand-green: #04b500;
  --brand-blue: #0689b0;
}
</style>
