<template lang="html">
  <div class="">
    <h1>Blogs</h1>
    <div class="" v-for="article in articles"
    :key="article._id">
    Author:<h6>{{ article.author }}</h6><br>
    Title:<h1>{{ article.title }}</h1>
    Body:<h2>{{ article.body }}</h2>
        <img :src="require('~/assets/' + article.imgpath)" style="height: 200px; width: 200px;">
    </div>
    <div class="" v-for="article in articles"
    :key="article._id">
    <div class="card" style="width: 18rem;">
  <img :src="require('~/assets/' + article.imgpath)" class="card-img-top" src="" alt="Card image cap">
  <div class="card-body">
    <h5 class="card-title">{{article.title}}</h5>
    <p class="card-text">{{article.body}}</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
</div>
  </div>
</template>

<script>
export default {
  middleware: 'auth',
  async asyncData(context){
    const {data} = await context.$axios.get('/api/articles/')
    return {
      articles : data,
    }
  },
}
</script>

<style lang="css">
</style>
