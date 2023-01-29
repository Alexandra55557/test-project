<template>
    <div class="person">
        <div class="person__image">
            <img src="@/assets/application/photo_1.png" alt="">
        </div>
        <div class="person__name">
            Юлия Дижа
        </div>
        <div class="person__description">
            Поможет запустить ваш проект
        </div>
    </div>
</template>

<script>
export default {
    name: 'person',
}
</script>

<style lang="scss">
    .person {
        display: flex;
        flex-flow: column;
        gap: 10px;

        &__image {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 200px;
            height: 200px;
            margin-bottom: 20px;

            img {
                width: 100%;
                height: 100%;
            }
        }

        &__name {
            font-weight: 600;
            font-size: 24px;
        }

        &__description {
            font-size: 18px;
        }
    }
</style>