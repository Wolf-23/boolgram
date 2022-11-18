<template>
    <div class="profileContainer">
        <div class="yourProfile">
            <img src="../../assets/images/profile.jpg" alt="Profile Pic" class="profileImg">
            <div>
                <h5>michelepapagni</h5>
                <h6>Michele Papagni</h6>
            </div>
        </div>
        <div>
            <a href="#" class="myLink">Passa a</a>
        </div>
    </div>
</template>
  
<script>
    export default {
        name: 'MyProfile'
    }
</script>

<style lang="scss">
    @import '../../assets/styles/mixin.scss';
    .profileContainer {
        width: 50%;
        height: 100%;
        @include betweenContent;
        .yourProfile {
           @include verticalAlign;
           h5, h6 {
            margin-left: 15px;
           }
           h6 {
            color: gray;
           }
        }
    }
</style>