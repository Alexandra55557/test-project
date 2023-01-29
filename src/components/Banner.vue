<template>
    <div class="banner">
        <img src="@/assets/banner.png" alt="">
    </div>
</template>

<script>
export default {
    name: 'banner',
}
</script>

<style lang="scss">
    .banner {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;

        img {
            width: 100%;
            height: 100%;
        }
    }
</style>