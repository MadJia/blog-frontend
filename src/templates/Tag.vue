<template>
  <Layout>
    <!-- Page Header -->
    <header class="masthead" style="background-image: url('/img/home-bg.jpg')">
      <div class="overlay"></div>
      <div class="container">
        <div class="row">
          <div class="col-lg-8 col-md-10 mx-auto">
            <div class="site-heading">
              <h1># {{$page.tag.title}}</h1>
            </div>
          </div>
        </div>
      </div>
    </header>

    <!-- Main Content -->
    <div class="container">
      <div class="row">
        <div class="col-lg-8 col-md-10 mx-auto">
          <div class="post-preview" v-for="post in $page.tag.posts" :key="post.id">
            <g-link :to="'/post/'+post.id">
              <h2 class="post-title">
                {{post.title}}
              </h2>
            </g-link>
              <hr>
          </div>
        </div>
      </div>
    </div>
  </Layout>
</template>

<page-query>
query ($id: ID!) {
  tag: strapiTags (id: $id){
    id
    title
    posts {
      id
      title
    }
  }
}

</page-query>

<script>
export default {
    name: 'TagPage'
}
</script>

<style>

</style>