<template>
    <div class="singleStory">
        <div v-if="loading == true" class="profileLoadingController">
            <div class="profileLoading"></div>
        </div>
        <div v-else @click="showStory = false">
            <img class="profileImg" :src="story.profile_picture" alt="Profile Img">
            <div class="profileName">{{ story.profile_name }}</div>
        </div>
        <div class="showStory" v-if="showStory == false">
            <i class="fa-solid fa-xmark" @click="showStory = true"></i>
            <div class="storyImg">
            <img src="../../../assets/images/landscape.png" alt="Show Story" >
            </div>
        </div>
    </div>
</template>
  
<script>
    export default {
        name: 'MySingleStory',
        props: {
            story: Object,
            loading: Boolean
        },
        data() {
            return {
                showStory: true
            }
        },
    }
</script>

<style lang="scss">
  @import '../../../assets/styles/mixin.scss';
  @import '../../../assets/styles/vars.scss';
    .singleStory {
        text-align: center;
        width: 100%;
        .profileImg {
            outline: 3px solid #00f4a3;
        }
        .profileName {
            margin-top: 3px;
            font-size: 11px;
            width: 100%;
        }
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
                cursor: auto;
            }
        }
        i {
                display: inline-block;
                position: absolute;
                right: 10px;
                top: 10px;
                font-size: 22px;
                color: $boolgram-primary;
                background-color: white;
                padding: 5px 8px;
                border-radius: 5px;
                cursor: pointer;
            }
    }
</style>