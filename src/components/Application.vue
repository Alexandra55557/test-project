<template>
    <div class="application" id="application">
        <div class="application__title">
            Оставте заявку
        </div>
        <div class="application__content">
            <div class="application__content--person">
                <Person />
            </div>
            <div class="application__content--fields">
                <Fields :error="error" v-model:name="name" v-model:number="number" v-model:description="description" />
            </div>
        </div>
        <div class="application__submit">
            <div class="application__submit--info">
                <Links />
            </div>
            <div class="application__submit--button" @click="send">
                <ButtonField text="Отправить" :isSubmit="true" />
            </div>
        </div>
    </div>
</template>

<script>
import Person from '@/components/application/Person.vue';
import Fields from '@/components/application/Fields.vue';
import ButtonField from '@/components/ui/ButtonField.vue';
import Links from '@/components/application/Links.vue';

export default {
    name: 'application',

    components: {
        Person,
        Fields,
        ButtonField,
        Links,
    },

    data() {
        return {
            error: false,
            name: '',
            number: '',
            description: '',
        }
    },

    methods: {
        send() {
            if (!this.name || !this.number || !this.description) {
                this.error = true;
            } else {
                this.error = false;
            }
        }
    }
}
</script>

<style lang="scss">
    .application {
        display: flex;
        flex-flow: column;
        padding: 55px 30px;
        gap: 25px;

        &__title {
            font-size: 48px;
            font-weight: 600;
        }

        &__content, &__submit {
            display: flex;
            flex-flow: row;
            gap: 150px;
        }

        @media (max-width: 600px) {
            
            &__content {
                flex-flow: column;
                gap: 30px;
            }

            &__submit {
                flex-flow: column-reverse;
                gap: 30px;
            }
        }
    }
</style>