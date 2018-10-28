<template>
  <section id="about-page" v-editable="aboutContent">
    <h1>{{ title }}</h1>
    <p>{{ content }}</p>
  </section>
</template>

<script>
  export default {
    asyncData(context) {
      console.log('cdn/stories/blog/' + context.route.name);
      return context.app.$storyapi.get('cdn/stories/about', {
        version: 'draft'
      }).then(res => {
        console.log(res.data)
        return {
          aboutContent: res.data.story.content,
          title: res.data.story.content.title,
          content: res.data.story.content.content
        }
      })
    },
    mounted(){
      this.$storyblok.init();
      this.$storyblok.on('change', () =>{
        location.reload(true);
      })
    }
  }
</script>

<style scoped>
  #about-page {
    width: 80%;
    max-width: 800px;
    margin: auto;
    padding: 30px 0;
  }
  #about-page p {
    white-space: pre-line;
  }
</style>
