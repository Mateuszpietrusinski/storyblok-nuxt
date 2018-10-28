<template>
  <nuxt-link
             :to="id">
    <article class="post-preview">
      <div
        :style="{backgroundImage: 'url('+thumbnailImage+')'}"
        class="post-preview-thumbnail">
        <div class="post-preview-content">
          <h1>{{title}}</h1>
          <p>{{excerpt}}</p>
        </div>
      </div>
    </article>
  </nuxt-link>
</template>
<script>


  export default {
   props: {
     title: {
       type: String,
       required: true
     },
     excerpt:{
       type: String,
       required: true
     },
     thumbnailImage: {
       type: String,
       required: true
     },
     id: {
       type: String,
       required: true
     }
   }
  }
</script>
<style scoped>
  a{
    text-decoration: none;
    color: #000;
  }
  a:first-of-type{
    margin-right: 0;
  }
  .post-preview{
    box-shadow: 1px 1px 5px 1px rgba(0,0,0,0.5);
    width: 90%;
    height: 20rem;
    margin: 1rem auto;
    position: relative;
  }
  .post-preview-thumbnail{
    background-position: center;
    background-size: cover;
    width: 100%;
    height: 160px;
  }
  .post-preview-content{
    text-align: center;
    padding: 1rem;
    position: absolute;
    bottom: 0;
  }
  @media (min-width: 35rem){
    .post-preview{
      width: 25rem;
    }
    a:first-of-type{
      margin-right: 30px;
    }
  }
</style>
