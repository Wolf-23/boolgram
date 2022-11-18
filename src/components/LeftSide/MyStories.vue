<template>
  <div>
    <div class="spinner" v-if="loading == true">
      <i class="fa-solid fa-spinner"></i>
    </div>
    <div class="storyContainer">
      <MySingleStory class="singleStory" v-for="(story, index) in listProfiles" :key="index" :story="story" :loading="loading"/>
    </div>
  </div>
</template>
  
<script>
  import MySingleStory from './SingleComponents/MySingleStory.vue'
  export default {
    name: 'MyStories',
    components: { 
      MySingleStory 
    },
    props: {
      listProfiles: Array,
      loading: Boolean
    }
  }
</script>
  
<style lang="scss">
  @import '../../assets/styles/mixin.scss';
  @import '../../assets/styles/vars.scss';
  .storyContainer {
    width: 100%;
    height: 100%;
    padding: 10px;
    position: relative;
    @include aroundContent;
    flex-wrap: nowrap;
    .singleStory {
      width: calc(100% / 7);
      cursor: pointer;
    }
    .profileLoadingController {
      width: 100%;
      @include aroundContent;
    }
    
  }
</style>