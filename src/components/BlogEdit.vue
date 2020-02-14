<template>
    <div class="col-sm-9 col-md-9 col-lg-9 mx-auto mt-4">
       <h2>New Post</h2>
       <form class="form-group mt-4">
           <label for="blogTitle"><h4>Blog Title</h4></label>
           <input 
                type="text" 
                class="form-control" 
                id="blogTitle"
                v-model="blogTitle">

           <label class="mt-3" for="blogBody"><h4>Blog Body</h4></label>
           <textarea 
                class="form-control no-resize" 
                name="entry" 
                id="blogBody" 
                cols="30" 
                rows="10"
                v-model="blogBody"></textarea>
            <button 
                class="btn btn-lg btn-dark mt-3"
                @click.prevent="postBlog">Post Blog</button>
       </form>
    </div>
</template>

<script>
import {eventBus} from '../main'

export default {
    data() {
        return {
            blogTitle: '',
            blogBody: ''
        }
    },
    methods: {
        postBlog() {
            eventBus.$emit('newBlog', { blogTitle: this.blogTitle, blogBody: this.blogBody });
            this.$router.push('/');
        }
    }
}
</script>

<style scoped>
    .no-resize {
        resize: none;
    }
</style>