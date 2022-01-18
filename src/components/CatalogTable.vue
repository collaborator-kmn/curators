<template>
        <v-data-table
            :headers="headers"
            :items="catalog"
            item-key="name"
            class="elevation-1">
            <template v-slot:[`item.curators`]="{ catalog }">
                <v-btn
                    class="ma-2"
                    color="primary"
                    dark
                >
                    Изменить
                <v-icon
                    small
                    class="mr-2"
                    @click.stop="$emit('edit', catalog)">
                    mdi-pencil
                </v-icon>
                </v-btn>
            </template>
        </v-data-table>
</template>

<script>
export default {
    props: ['catalog'],

    data: () => ({}),

    computed: {
        headers() {
            return [
                {
                    text: 'АРМ',
                    value: 'arm',
                },
                {
                    text: 'АРМ Босс',
                    value: 'boss'
                },
                {
                    text: 'Кураторы',
                    value: 'curators'
                }
            ]
        },
    }
}
</script>
