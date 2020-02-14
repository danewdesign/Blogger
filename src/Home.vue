<template>
  <div class="row mt-5">
    <div class="col-sm-12 col-md-9 col lg-9">
      <div class="card ml-5 mr-5">
        <div class="card-header alert-light text-info">
          <h3>Sample Title</h3>
          <small>
            <em>{{ getDate() }}</em>
          </small>
        </div>
        <div class="card-body">
          <p class="mt-2">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
            aliquip ex ea commodo consequat. Duis aute irure dolor in
            reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
            pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
            culpa qui officia deserunt mollit anim id est laborum.
          </p>
        </div>
      </div>
      <!-- <ul>
        <li v-for="blog in blogs"> -->
      <div
        class="card ml-5 mr-5 mt-5"
        v-for="blog in blogs"
        :key="blog.id"
      >
        <div class="card-header alert-light text-info">
          <h3>{{ blog.blogTitle }}</h3>
          <small>
            <em>{{ getDate() }}</em>
          </small>
        </div>
        <div class="card-body">
          <p>{{ blog.blogBody }}</p>
        </div>
      </div>
      <!-- </li>
      </ul> -->
    </div>
    <div class="col-sm-12 col-md-3 col-lg-3 v-hr mt-4">
      <blog-history></blog-history>
    </div>
  </div>
</template>

<script>
import History from "./components/History";
import { eventBus } from "./main";

export default {
  data() {
    return {
      blogs: []
    };
  },
  methods: {
    getDate() {
      const timeNow = new Date();
      return timeNow.toLocaleDateString();
    }
  },
  computed: {},
  components: {
    "blog-history": History
  },
  created() {
    eventBus.$on("newBlogTitle", data => {
      console.log(data);
      this.blogs.push(data);
    });
  }
};
</script>

<style scoped>
ul {
  padding-left: 0;
}

li {
  list-style-type: none;
}
</style>
