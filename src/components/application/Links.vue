<template>
    <div class="links">
        <div class="links__title">
            Скачать брифинги на:
        </div>
        <div class="links__content">
            <div class="links__content--each" v-for="item, index in items" :key="index">
                <div class="links__content--each__text">
                    {{ item }}
                </div>
                <div class="links__content--each__arrow">
                    <img src="@/assets/application/arrow.png" alt="">
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'links',

    data() {
        return {
            items: [
                'разработку логотипа',
                'разработку сайта',
                'разработку лендинга'
            ]
        }
    }
}
</script>

<style lang="scss">
    .links {
        display: flex;
        flex-flow: column;
        gap: 20px;

        &__title {
            font-size: 24px;
            font-weight: 600;
        }

        &__content {
            display: flex;
            flex-flow: column;
            gap: 10px;

            &--each {
                color: #D22020;
                text-decoration: underline;
                display: flex;
                flex-flow: row nowrap;
                gap: 10px;
                font-size: 18px;
                cursor: pointer;
            }
        }
    }
</style>