<template>
    <div>
        <div class="suggestedHeader">
            <strong class="suggested">Suggerimenti per te:</strong>
            <a class="suggestedLink myLink" href="#" @click="showSuggested = !showSuggested">Mostra tutti</a>
        </div>
        <div v-if="loading == true">
            <div class="loadingSuggested" v-for="(profile, index) in listProfiles" :key="index">
                <div class="profileLoading"></div>
                <div class="profileNameLoading"></div>
            </div>
        </div>
        <div v-else>
            <div  v-if="showSuggested == true">
                <div class="singleProfileCont" v-for="(profile, index) in listProfiles.slice(0,4)" :key="index">
                    <img class="profileImg" :src="profile.profile_picture" alt="Profile Img">
                    <span class="profileName">{{ profile.profile_name }}</span>
                </div>
            </div>
            <div v-else class="singleProfileCont" v-for="(profile, x) in listProfiles" :key="x">
                <img class="profileImg" :src="profile.profile_picture" alt="Profile Img">
                <span class="profileName">{{ profile.profile_name }}</span>
            </div>
        </div>
    </div>
</template>
  
<script>
    export default {
        name: 'MySuggested',
        props: {
            listProfiles: Array,
            loading: Boolean
        },
        data() {
            return {
                showSuggested: true,
            }
        }
    }
</script>

<style lang="scss">
@import '../../assets/styles/vars.scss';
@import '../../assets/styles/mixin.scss';
    .suggestedHeader {
        margin-bottom: 35px;
        @include betweenContent;
        .suggested {
            color: #000;
        }
    }
    .singleProfileCont {
        display: flex;
        align-items: center;
        margin: 15px 0;
        .profileName {
            margin-left: 10px;
            color: #000;
        }
    }

    .loadingSuggested {
        display: flex;
        align-items: center;
        margin: 15px 0;
        .profileNameLoading {
            height: 20px;
            width: 150px;
            background-color: lightgray;
            margin-left: 10px;
        }
    }
</style>