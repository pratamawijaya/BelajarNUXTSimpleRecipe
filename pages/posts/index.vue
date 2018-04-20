<template>
   <ul v-if="posts && posts.length">
    <li v-for="post of posts">
      <p><strong>{{post.title}}</strong></p>
      <p>{{post.body}}</p>
    </li>
  </ul>

  <ul v-else-if="errors && errors.length">
    <li v-for="error of errors">
      {{error.message}}
    </li>
  </ul>
</template>

<script>
import axios from 'axios';
export default {
    data() {
        return {
            posts: [],
            errors: []
        }
    },

    created() {
        axios.get('http://jsonplaceholder.typicode.com/posts')
        .then(response => {
            this.posts = response.data
        })
        .catch(e => {
            this.errors.push(e)
        })
    }
  
}
</script>
