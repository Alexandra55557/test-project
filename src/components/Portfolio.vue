<template>
    <div class="portfolio" id="portfolio">
        <div class="portfolio__header">
            <div class="portfolio__header--title">
                Портфолио
            </div>
            <div class="portfolio__header--all">
                <div class="portfolio__header--all__text">
                    СМОТРЕТЬ ВСЕ
                </div>
                <div class="portfolio__header--all__image">
                    <img src="@/assets/portfolio/arrow.png" alt="">
                </div>
            </div>
        </div>
        <div class="portfolio__cards">
            <div class="portfolio__cards--each" v-for="card, index in computedCards" :key="index">
                <Card :card="card" />
            </div>
        </div>
        <div class="portfolio__button">
            <ButtonField text="ВСЕ КЕЙСЫ" size="18px" />
        </div>
    </div>
</template>

<script>
import Card from '@/components/portfolio/Card.vue';
import ButtonField from '@/components/ui/ButtonField.vue';

export default {
    name: 'portfolio',

    components: {
        Card,
        ButtonField,
    },

    data() {
        return {
            cards: [
                {
                    image: '/src/assets/portfolio/frame_1.png',
                    title: '«Натали» — Ивановский трикотаж оптом',
                },
                {
                    image: '/src/assets/portfolio/frame_2.png',
                    title: 'Podium — эротический массаж',
                },
                {
                    image: '/src/assets/portfolio/frame_3.png',
                    title: 'Аудит отдела маркетинга и продаж для Название бренда длинное название...',
                },
                {
                    image: '/src/assets/portfolio/frame_4.png',
                    title: 'Аудит отдела маркетинга и продаж для Название бренда',
                },
                {
                    image: '/src/assets/portfolio/frame_5.png',
                    title: 'Аудит отдела маркетинга и продаж для Название бренда',
                },
                {
                    image: '/src/assets/portfolio/frame_6.png',
                    title: 'Аудит отдела маркетинга и продаж для Название бренда',
                },
            ],
            computedCards: [],
        }
    },


    methods: {
        changeCards() {
            if (window.innerWidth > 600) {
                this.computedCards = this.cards;
            } else {
                this.computedCards = this.cards.slice(0, 2);
            }
        }
    },

    mounted() {
        this.changeCards();
        window.addEventListener('resize', () => {
            this.changeCards();
        })
    }
}
</script>

<style lang="scss">
    .portfolio {
        display: flex;
        flex-flow: column;
        padding: 55px 30px;
        gap: 30px;

        &__header {
            display: flex;
            justify-content: space-between;

            &--title {
                font-size: 48px;
                font-weight: 600px;
            }

            &--all {
                display: flex;
                flex-flow: row nowrap;
                align-items: center;
                gap: 15px;
                
                &__text {
                    color: #D22020;
                    font-size: 18px;
                }

                &__image {
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    width: 16px;
                    height: 16px;

                    img {
                        width: 100%;
                        height: 100%;
                    }
                }
            }

            @media (max-width: 600px) {
                flex-flow: column;
                gap: 20px;
            }
        }

        &__cards {
            display: flex;
            flex-flow: row wrap;
            justify-content: center;
            gap: 25px;
        }

        &__button {
            margin: 40px auto 0 auto;
        }
    }
</style>