<template>
    <div class="footer-block">
        <div class="footer-block__terms">
            <div class="footer-block__terms--drozzi">
                2015-2021 © Дрожжи™
            </div>
            <div class="footer-block__terms--market">
                ООО «РВБ-Маркетинг»
            </div>
            <div class="footer-block__terms--policy">
                Политика конфиденциальности
            </div>
        </div>
        <div class="footer-block__logo">
            <img src="@/assets/footer/logo.png" alt="">
        </div>
    </div>
</template>

<script>
export default {
    name: 'footer-block',

}
</script>

<style lang="scss">
    .footer-block {
        border: 1px solid #ACB5BD;
        display: flex;
        flex-flow: column;
        align-items: center;
        gap: 15px;
        padding: 25px;

        &__terms {
            display: flex;
            flex-flow: row;
            justify-content: center;
            gap: 10px;

            * {
                color: #ADB5BD;
                font-size: 18px;
            }

            &--policy {
                cursor: pointer;
                user-select: none;
            }

            @media (max-width: 600px) {
                flex-flow: column;

                * {
                    text-align: center;
                }
            }
        }

        &__logo {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100px;

            img {
                width: 100%;
                height: 100%;
            }
        }
    }
</style>