<template>
  <div>
    <MyHeader/>
    <MyMain :listProfiles="listProfiles" :listPosts="listPosts" :loading="loading"/>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue';
import axios from 'axios';

export default {
  name: 'App',
  data() {
    return {
      listProfiles: [],
      listPosts: [],
      loading: true
    }
  },
  components: {
    MyHeader,
    MyMain
  },
  methods: {
    
    apiRequestProfiles() {
      axios.get('https://flynn.boolean.careers/exercises/api/boolgram/profiles')
      .then(response => {
        this.listProfiles = response.data;
        setTimeout ( () => {
          this.loading = false;
        }, 3000);
      })
      .catch(err => {
        console.log(err);
      })
    },

    apiRequestPosts() {
      axios.get('https://flynn.boolean.careers/exercises/api/boolgram/posts')
      .then(response => {
        this.listPosts = response.data;
        setTimeout ( () => {
          this.loading = false;
        }, 3000);
      })
      .catch(err => {
        console.log(err);
      })
    },
  },
  mounted() {
    this.apiRequestProfiles();
    this.apiRequestPosts();
  }
}
</script>

<style lang="scss">
  @import '~@fortawesome/fontawesome-free/css/all.css';
  @import './assets/styles/general.scss';
  @import './assets/styles/vars.scss';
  @import './assets/styles/mixin.scss';
</style>

