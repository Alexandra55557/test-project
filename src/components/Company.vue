<template>
    <div class="company" id="company">
        <div class="company__title">
            О компании
        </div>
        <div class="company__subtitle">
            <div class="company__subtitle--each" v-for="item, index in items" :key="index">
                <Info :item="item" />
            </div>
        </div>
        <div class="company__content">
            <div class="company__content--left">
                <LeftBlock />
            </div>
            <div class="company__content--right">
                <img src="@/assets/company/company.png" data-fancybox="gallery" alt="">
            </div>
        </div>
    </div>
</template>

<script>
import Info from '@/components/company/Info.vue';
import LeftBlock from '@/components/company/LeftBlock.vue';
import "@fancyapps/ui/dist/fancybox.css";
import { Fancybox, Carousel, Panzoom } from "@fancyapps/ui";

export default {
    name: 'company',

    components: {
        Info,
        LeftBlock,
    },

    data() {
        return {
            items: [
                {
                    number: '5',
                    who: 'отделов'
                },
                {
                    number: '5',
                    who: 'маркетологов'
                },
                {
                    number: '3',
                    who: 'дизайнера'
                },
                {
                    number: '3',
                    who: 'копирайтера'
                },
                {
                    number: '7',
                    who: 'разработчиков'
                },
            ]
        }
    }
}
</script>

<style lang="scss">
    .company {
        display: flex;
        gap: 50px;
        flex-flow: column;
        padding: 55px 30px;

        &__title {
            font-size: 48px;
            font-weight: 600;
        }

        &__subtitle {
            display: flex;
            flex-flow: row;
            gap: 30px;

            @media (max-width: 600px) {
                flex-flow: column;
            }
        }

        &__content {
            display: flex;
            flex-flow: row;

            &--left {
                max-width: 50%;
            }

            &--right {
                display: flex;
                justify-content: center;
                align-items: center;
                max-width: 50%;
                cursor: pointer;

                img {
                    width: 100%;
                    height: 100%;
                }
            }

            @media (max-width: 600px) {
                flex-flow: column;
                gap: 20px;

                &--left, &--right {
                    max-width: unset;
                }
            }
        }
    }
</style>