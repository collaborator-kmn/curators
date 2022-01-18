<template>
    <div>
        <v-data-table
            :headers="headers"
            :items="catalog"
            item-key="name"
            class="elevation-1">
            <template v-slot:body.append>
                <tr>
                    <td></td>
                    <td colspan="4"></td>
                </tr>
            </template>
        </v-data-table>
    </div>
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
