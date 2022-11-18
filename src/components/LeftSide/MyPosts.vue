<template>
    <div class="singlePostContainer">
      <MySinglePost v-for="(post, index) in listPosts" :key="index" :post="post" :loading="loading"/>
    </div>
  </template>
  
<script>
  import MySinglePost from './SingleComponents/MySinglePost.vue'
  export default {
    name: 'MyPosts',
    components: { 
      MySinglePost 
    },
    props: {
      listPosts: Array,
      loading: Boolean
    },
  }
</script>
  
<style lang="scss">
  .singlePostContainer {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  ::-webkit-scrollbar {
    width: 8px;
  }
  ::-webkit-scrollbar-thumb {
      background: linear-gradient(180deg, #0064fb 0%, #00f4a3 100%);
      border-radius: 10px;
  }
</style>