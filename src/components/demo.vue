<template>
<ul v-if="posts && posts.length">
    <li v-for="post in posts" :key="post.userName">
      <p><strong>{{post.userName}}</strong></p>
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

  // lấy dữ liệu khi component được tạo thành công
  created() {
    axios.get(`http://localhost:1998/get-all-accounts`)
    .then(response => {
      this.posts = response.data.data
    })
    .catch(e => {
      this.errors.push(e)
    })
  }
}
</script>