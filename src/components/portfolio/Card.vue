<template>
    <div class="card">
        <div class="card__image">
            <img :src="card.image" alt="">
        </div>
        <div class="card__title">
            {{ card.title }}
        </div>
    </div>
</template>

<script>
export default {
    name: 'card',

    props: {
        card: {
            type: Object,
            default: {},
        }
    },
}
</script>

<style lang="scss">
    .card {
        display: flex;
        flex-flow: column;
        gap: 10px;
        cursor: pointer;

        &__image {
            width: 630px;
            height: 515px;
            display: flex;
            justify-content: center;
            align-items: center;

            img {
                width: 100%;
                height: 100%;
            }
        }

        &__title {
            font-size: 24px;
            max-width: 630px;
        }

        @media (max-width: 650px) {
            &__image {
                width: 100%;
            }

            &__title {
                width: 100%;
            }
        }
    }
</style>