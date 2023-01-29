<template>
    <div class="burger" @click="open">
        <div class="burger__open" v-show="!active">
            <img src="@/assets/burger.png" alt="">
        </div>
        <div class="burger__close" v-show="active">
            <img src="@/assets/close.png" alt="">
        </div>
    </div>
</template>

<script>

export default {
    name: 'burger',
    
    data() {
        return {
            active: false,
        }
    },

    methods: {
        open() {
            this.active = !this.active;
            this.$emit('open', this.active);
        }
    }
}
</script>

<style lang="scss">
    .burger {
        &__open, &__close {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 20px;
            height: 20px;

            img {
                width: 100%;
                height: 100%;
            }
        }
    }
</style>