<template>
  <div>
     <blog-header></blog-header>
     <div class="container-fluid">
         <router-view></router-view>
     </div>
  </div>
</template>

<script>
import Header from "./Header.vue";

export default {
  computed: {
 
  },
  components: {
    "blog-header": Header
  }
};
</script>

<style>
    .v-hr {
        border-left: solid 2px lightslategray;
    
    }
</style>
