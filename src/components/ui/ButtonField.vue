<template>
    <div class="button-field" :class="{'button-field__submit': isSubmit}">
        {{ text }}
    </div>
</template>

<script>
export default {
    name: 'button-field',

    props: {
        text: {
            type: String,
            default: '',
        },

        isSubmit: {
            type: Boolean,
            default: false,
        },

        size: {
            type: String,
            default: '24px',
        }
    }
}
</script>

<style lang="scss">
    .button-field {
        color: #D22020;
        border: 1px solid #D22020;
        transition: border .3s;
        transition: color .3s;
        border-radius: 56px;
        padding: 20px 70px;
        width: fit-content;
        user-select: none;
        cursor: pointer;
        font-size: v-bind(size);

        &__submit {
            background: #D22020;
            transition: background .3s;
            color: #fff;
        }

        &__submit:hover {
            background: #840000;
            transition: background .3s;
            color: #fff !important;
        }
    }

    .button-field:hover {
        border: 1px solid #840000;
        color: #840000;
        transition: border .3s;
        transition: color .3s;
    }
</style>