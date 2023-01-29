<template>
    <div class="left-block">
        <div class="left-block__content">
            Мы — команда специалистов с опытом, энтузиазмом и лёгким недосыпом. Маркетинговое агентство «Дрожжи» было основано 
            в 2015 году, как компания, где можно получить комплексное интернет- и oффлайн-продвижение. На сегодняшний день мы не зависим ни от ниши, ни от географии, ни от специфики продукта. 
            В портфолио компании сотни успешных кейсов, способных помочь вам в реализации своей идеи.
        </div>
        <div class="left-block__info">
            <div class="left-block__info--each" v-for="item, index in items" :key="index">
                <div class="left-block__info--each__count">
                    {{ item.count }}
                </div>
                <div class="left-block__info--each__what">
                    {{ item.what }}
                </div>
            </div>
        </div>
        <div class="left-block__button">
            <ButtonField text="ПОДРОБНЕЕ" size="18px" />
        </div>
    </div>
</template>

<script>
import ButtonField from '@/components/ui/ButtonField.vue';

export default {
    name: 'left-block',

    components: {
        ButtonField,
    },

    data() {
        return {
            items: [
                {
                    count: '1000+',
                    what: 'реализованных проектов'
                },
                {
                    count: '92',
                    what: 'клиента доверили нам свои проекты'
                },
                {
                    count: '5+',
                    what: 'лет успешной работы'
                },
            ]
        }
    }

}
</script>

<style lang="scss">
    .left-block {
        display: flex;
        flex-flow: column;
        gap: 50px;

        &__content {
            font-size: 18px;
            line-height: 27px;
        }

        &__info {
            display: flex;
            flex-flow: row nowrap;
            gap: 30px;

            &--each {
                display: flex;
                flex-flow: column;
                gap: 10px;

                &__count {
                    font-size: 40px;
                    font-weight: 600;
                    color: #D22020;
                }

                &__what {
                    font-size: 18px;
                }
            }

            @media (max-width: 600px) {
                flex-flow: column;
            }
        }

        @media (max-width: 600px) {
            &__button {
                margin: 0 auto;
            }
        }
    }
</style>