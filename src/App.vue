<template>
  <div>
     <blog-header></blog-header>
     <div class="container-fluid">
         <router-view :blogs="blogs" />
     </div>
  </div>
</template>

<script>
import Header from "./Header.vue";
import {eventBus} from './main'

export default {
  data() {
    return {
      blogs: []
    };
  },
  components: {
    "blog-header": Header
  },
  created() {
    eventBus.$on("newBlog", data => {
      this.blogs.push(data);
    });
  }
};
</script>

<style>
    .v-hr {
        border-left: solid 2px lightslategray;
    
    }
</style>
