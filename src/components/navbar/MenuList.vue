<template>
    <div class="menu-list" :class="{'menu-list__mobile': active}">
        <div class="menu-list__portfolio" @click="close">
            <a href="#portfolio">Портфолио</a>
        </div>
        <div class="menu-list__company" @click="close">
            <a href="#company">О компании</a>
        </div>
        <div class="menu-list__contacts" @click="close">
            <a href="#application">Контакты</a>
        </div>
        <div class="menu-list__application" v-if="!active">
            <a href="#application">Оставьте заявку</a>
        </div>
    </div>
</template>

<script>
export default {
    name: 'menu-list',

    props: {
        active: {
            type: Boolean,
            default: false,
        }
    },

    methods: {
        close() {
            this.$emit('update:active', false);
        }
    }
}
</script>

<style lang="scss">
    .menu-list {
        display: flex;
        flex-flow: row nowrap;
        gap: 15px;

        &__mobile {
            position: absolute;
            top: 80px;
            left: 0;
            right: 0;
            bottom: 0;
            background: #fff;
            flex-flow: column;
            width: 100%;
            height: 1000px;
            padding: 20px;
        }

        * {
            cursor: pointer;
            display: flex;
            align-items: center;
            user-select: none;

            a {
                color: #000;
                text-decoration: none;
            }
        }

        &__application {
            background: #D22020;
            border-radius: 50px;
            padding: 10px 20px;
            
            a {
                color: #fff;
            }
        }
    }
</style>