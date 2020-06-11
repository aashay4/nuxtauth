<template>
  <div>
    <h1>Home</h1>
    <hr>
    <h3>Welcome to Express CRUD</h3>
      <div v-for="article in articles"
      :key="article._id">
      <b>{{ article.title }}</b><br>
      <b>{{ article.author }}</b><br>
      <b>{{ article.body }}</b><br><hr>

      <h1 v-if="$auth.loggedIn">Log out</h1>
    </div>
    </nuxt-link>
  </div>
</template>
<script>
export default {
  async asyncData(context){
    const {data} = await context.$axios.get('/api/articles')
    return {
      articles : data
    }
  },
}
</script>
