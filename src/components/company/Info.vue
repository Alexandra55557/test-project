<template>
    <div class="info">
        <div class="info__number">
            {{ item.number }}
        </div>
        <div class="info__who">
            {{ item.who }}
        </div>
    </div>
</template>

<script>
export default {
    name: 'info',

    props: {
        item: {
            type: Object,
            default: {},
        }
    }
}
</script>

<style lang="scss">
    .info {
        display: flex;
        flex-flow: row nowrap;
        gap: 12px;

        &__number {
            color: #D22020;
            font-size: 32px;
        }

        &__who {
            font-size: 32px;
        }
    }
</style>