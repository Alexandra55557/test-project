<template>
    <div class="input-field">
        <input type="text" :placeholder="placeholder" :value="name" @input="$emit('update:name', $event.target.value)">
    </div>
</template>

<script>
export default {
    name: 'name-input-field',

    props: {
        placeholder: {
            type: String,
            default: '',
        },

        name: {
            type: String,
            default: '',
        }
    },
}
</script>

<style lang="scss">
    .input-field {
        width: 100%;
        input {
            width: 100%;
            font-size: 18px;
            border: 0;
            outline: 0;
            border-bottom: 1px solid #CED4DA;
            padding-bottom: 20px;
        }

        input::placeholder {
            font-size: 24px;
            color: #ACB5BD;
        }
    }
</style>