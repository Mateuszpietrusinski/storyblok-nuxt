<template>
  <div class="main-content">
    <TheHeader />
    <nuxt/>
  </div>
</template>

<script>
  import TheHeader from '@/components/TheHeader/TheHeader'

  export default {
    components:{
      TheHeader
    }
  }
</script>

<style>
  * {
    box-sizing: content-box;
  }
  body{
    font-family: "Lato",sans-serif;
    margin: 0;
  }
  .main-content{
    margin-top: 4.5rem;
  }
</style>
