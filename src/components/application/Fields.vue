<template>
    <div class="fields">
        <div class="fields__name">
            <NameInputField placeholder="Ваше имя*" v-model:name="name1" />
        </div>
        <div class="fields__contact">
            <NumberInputField placeholder="Телефон или мессенджер*" v-model:number="number1" />
        </div>
        <div class="fields__description">
            <TextField v-model:description="description1"  />
        </div>
        <div class="fields__error" :class="{'fields__error--display': error}">
            Заполните не достающие поля *
        </div>
    </div>
</template>

<script>
import NameInputField from '@/components/ui/NameInputField.vue';
import NumberInputField from '@/components/ui/NumberInputField.vue';
import TextField from '@/components/ui/TextField.vue';

export default {
    name: 'fields',

    components: {
        TextField,
        NameInputField,
        NumberInputField,
    },

    props: {
        error: {
            type: Boolean,
            default: false,
        },

        name: {
            type: String,
            default: '',
        },

        number: {
            type: String,
            default: '',
        },

        description: {
            type: String,
            default: '',
        },
    },

    data() {
        return {
            name1: '',
            number1: '',
            description1: '',
        }
    },

    watch: {
        name1() {
            this.$emit('update:name', this.name1);
        },

        number1() {
            this.$emit('update:number', this.number1);
        },

        description1() {
            this.$emit('update:description', this.description1);
        },
    },

    mounted() {
        this.name1 = this.name;
        this.number1 = this.number;
        this.description1 = this.description;
    }
}
</script>

<style lang="scss">
    .fields {
        display: flex;
        flex-flow: column;
        gap: 45px;
        width: 560px;

        &__error {
            color: #D22020;
            font-size: 14px;
            opacity: 0;
            transition: opacity .5s;

            &--display {
                opacity: 1;
                transition: opacity .5s;
            }
        }
    }
</style>