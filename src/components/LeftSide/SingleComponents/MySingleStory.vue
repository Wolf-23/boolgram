<template>
    <div class="singleStory">
        <div v-if="loading == true" class="profileLoadingController">
            <div class="profileLoading"></div>
        </div>
        <div v-else>
            <img class="profileImg" :src="story.profile_picture" alt="Profile Img">
            <div class="profileName">{{ story.profile_name }}</div>
        </div>
    </div>
</template>
  
<script>
    export default {
        name: 'MySingleStory',
        props: {
            story: Object,
            loading: Boolean
        }
    }
</script>

<style lang="scss">
    .singleStory {
        text-align: center;
        width: 100%;
        img {
            outline: 3px solid #00f4a3;
        }
        .profileName {
            margin-top: 3px;
            font-size: 11px;
            width: 100%;
        }
    }
</style>