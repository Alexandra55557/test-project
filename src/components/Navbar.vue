<template>
    <div class="navbar">
        <div class="navbar__logo">
            <img src="@/assets/logo.png" alt="">
        </div>
        <div class="navbar__buttons">
            <MenuList v-if="!isMobile || active" v-model:active="active" />
            <Burger v-if="isMobile" @open="open" />
        </div>
    </div>
</template>

<script>
import MenuList from '@/components/navbar/MenuList.vue';
import Burger from '@/components/navbar/Burger.vue';

export default {
    name: 'navbar',

    components: {
        MenuList,
        Burger,
    },

    data() {
        return {
            isMobile: false,
            active: false,
        }
    },

    methods: {
        checkMobile() {
            if (window.innerWidth > 600) {
                this.isMobile = false;
            } else {
                this.isMobile = true;
            }
        },

        open(active) {
            this.active = active;
        }
    },

    watch: {
        active() {
            if (this.active) {
                document.documentElement.style.overflowY = 'hidden';
            } else {
                document.documentElement.style.overflowY = 'auto';
            }
        }
    },

    mounted() {
        this.checkMobile();
        window.addEventListener('resize', this.checkMobile);
    }
}
</script>

<style lang="scss">
    .navbar {
        display: flex;
        flex-flow: row nowrap;
        justify-content: space-between;
        align-items: center;
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        padding: 25px 30px;
        background: rgb(232, 232, 232);

        &__logo {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100px;
            height: 45px;

            img {
                width: 100%;
                height: 100%;
            }
        }
    }
</style>