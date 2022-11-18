<template>
  <div>
    <div class="spinner" v-if="loading == true">
      <i class="fa-solid fa-spinner"></i>
    </div>
    <div class="storyContainer" @click="showStory = !showStory">
      <MySingleStory class="singleStory" v-for="(story, index) in listProfiles" :key="index" :story="story" :loading="loading"/>
      <div class="showStory" v-if="showStory == false">
        <i class="fa-solid fa-xmark" @click="showStory"></i>
        <div class="storyImg">
          <img src="../../assets/images/landscape.png" alt="Show Story" >
        </div>
      </div>
    </div>
  </div>
</template>
  
<script>
  import MySingleStory from './SingleComponents/MySingleStory.vue'
  export default {
    name: 'MyStories',
    data() {
            return {
                showStory: true
            }
        },
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
    .showStory {
      position: absolute;
      width: 500px;
      height: 500px;
      top: 50%;
      left: 50%;
      .storyImg {
        @include centredContent;
        width: 100%;
        height: 100%;
        img {
          width: 500px;
          height: 500px;
        }
      }
      i {
        position: absolute;
        right: 10px;
        top: 10px;
        // font-size: 22px;
        color: $boolgram-primary;
        background-color: white;
        padding: 5px;
        border-radius: 10px;
        cursor: pointer;
      }
    }
  }
</style>