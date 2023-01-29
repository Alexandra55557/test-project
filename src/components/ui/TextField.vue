<template>
    <div class="text-field">
        <textarea name="" id="" cols="30" rows="10" placeholder="Краткое описание задачи*"  :value="description" @input="$emit('update:description', $event.target.value)"></textarea>
    </div>
</template>

<script>
export default {
    name: 'text-field',

    props: {
        description: {
            type: String,
            default: '',
        }
    }
}
</script>

<style lang="scss">
    .text-field {
        width: 100%;

        textarea {
            width: 100%;
            border: 0;
            outline: 0;
            border-bottom: 1px solid #CED4DA;
            font-size: 18px;
        }

        textarea::placeholder {
            font-size: 24px;
            color: #ACB5BD;
        }

    }
</style>