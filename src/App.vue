<template>
 <v-app id="app">
    <Navbar/>   
    <v-content  class="mx-4">
      <router-view></router-view>
    </v-content>     
  </v-app>
</template>



<script>
import Navbar from '@/components/Navbar'
export default {
  name: 'App',
  components: { Navbar },

  data: () => ({
    //
  }),
};
</script>

<style>
  #app {
    background-color: #F5F5F5;
}
</style>
