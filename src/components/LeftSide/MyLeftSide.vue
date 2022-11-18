<template>
    <div>
      <MyStories class="stories" :listProfiles="listProfiles" :loading="loading"/>
      <MyPosts class="posts" :listPosts="listPosts" :loading="loading"/>
    </div>
</template>
  
<script>
    import MyStories from './MyStories.vue'
    import MyPosts from './MyPosts.vue';
    export default {
        name: 'MyLeftSide',
        components: {
        MyStories,
        MyPosts
    },
    props: {
      listProfiles: Array,
      listPosts: Array,
      loading: Boolean
    }
}
</script>

<style scoped lang="scss">
    .stories {
        width: 100%;
        height: 150px;
        margin: 25px 0;
    }
    .posts {
        width: 100%;
        height: calc(100% - 220px);
        margin-bottom: 20px;
        overflow-y: auto;
    }
    .posts, .stories {
        background-color: #fff;
        border: 1px solid lightgray;
        border-radius: 10px;
    }

</style>