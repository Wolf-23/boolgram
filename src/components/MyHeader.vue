<template>
  <header>
    <div class="headerContainer container">
      <div class="logo">
        <img src="../assets/images/logo.png" alt="Boolgram Logo">
      </div>
      <div class="search">
        <input type="search" name="search" id="search" placeholder="Cerca">
      </div>
      <div class="icons">
        <i class="fa-regular fa-heart"></i>
        <i class="fa-solid fa-house"></i>
        <img src="../assets/images/profile.jpg" alt="Profile Pic" class="profilePic">
      </div>
    </div>
  </header>
</template>

<script>
  export default {
    name: 'MyHeader'
  }
</script>

<style lang="scss">
 @import '../assets/styles/mixin.scss';
 @import '../assets/styles/vars.scss';
  header {
    height: 8vh;
    background-color: #fff;
    border-bottom: 1px solid lightgray;
    .headerContainer {
      height: 100%;
      @include betweenContent;
    }
    .logo, .search, .icons {
      width: calc(100% / 3);
    }
    .logo {
      img {
        width: 100px;
      }
    }
    .search {
      text-align: center;
      input {
        text-align: center;
        border-radius: 15px;
        border: 1px solid gray;
        padding: 3px 15px;
      }
    }
    .icons {
      display: flex;
      align-items: center;
      justify-content: end;
      i, img {
        padding: 0 15px;
      }
      i{
        &:hover{
          color: $boolgram-primary;
        }
      }
    }
  }
</style>