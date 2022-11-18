<template>
    <footer>
        <h5 class="footertext"> 
            <i class="fa-regular fa-copyright"></i>
            2020 INSTAGRAM FROM FACEBOOK</h5>
    </footer>
</template>
  
<script>
    export default {
        name: 'MyFooter'
    }
</script>

<style lang="scss" scoped>
@import '../../assets/styles/vars.scss';
    .footertext {
        color: $boolgram-primary;
        i{
            font-size: 12px;
        }
    }
</style>