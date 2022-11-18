<template>
    <div class="rightSide">
      <MyProfile class="profile"/>
      <MySuggested class="suggested" :listProfiles="listProfiles" :loading="loading"/>
      <MyFooter class="footer"/>
    </div>
</template>
  
<script>
    import MyFooter from './MyFooter.vue'
    import MyProfile from './MyProfile.vue'
    import MySuggested from './MySuggested.vue'
    export default {
        name: 'MyRightSide',
        components: { 
            MyProfile, 
            MySuggested, 
            MyFooter 
        },
        props: {
            listProfiles: Array,
            loading: Boolean
        }
    }
</script>

<style lang="scss">
    .rightSide {
        padding: 5px;
        .profile {
            width: 100%;
            height: 60px;
            margin: 50px 0;
        }
        .suggested {
            height: calc(100% - 185px)
        }
        .footer {
            height: 25px;
        }
    }
</style>