<template>
  <main>
    <div class="container">
      <MyLeftSide class="leftSide" :listProfiles="listProfiles" :listPosts="listPosts" :loading="loading"/>
      <MyRightSide class="rightSide" :listProfiles="listProfiles" :loading="loading"/>
    </div>
    </main>
</template>

<script>
import MyLeftSide from './LeftSide/MyLeftSide.vue'
import MyRightSide from './RightSide/MyRightSide.vue'
  export default {
    name: 'MyMain',
    components: { 
      MyLeftSide,
      MyRightSide 
    },
    props: {
      listProfiles: Array,
      listPosts: Array,
      loading: Boolean
    }
  }
</script>

<style scoped lang="scss">

  main {
    height: 92vh;
    background-color: rgb(242, 242, 242);
    .container {
      display: flex;
      justify-content: space-between;
      height: 100%;
      .leftSide {
        width: 55%;
        height: 100%;
      }
      .rightSide {
        width: 40%;
        height: 100%;
      }
    }
    
  }

</style>