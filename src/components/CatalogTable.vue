<template>
        <v-data-table
            :headers="headers"
            :items="catalog"
            item-key="name"
            class="elevation-1">
            <template v-slot:[`item.curators`]="{ item }">
                <v-icon
                    small
                    class="mr-4"
                    @click.stop="onEdit(item)">
                    mdi-pencil
                </v-icon>
                <template>
                    <v-dialog v-model="dialog" max-width="750">
                       <catalog-item/>
                    </v-dialog>
            </template>
            </template>
        </v-data-table>
</template>

<script>
import CatalogItem from "@/components/CatalogItem";
export default {
    components: {CatalogItem},
    props: ['catalog'],

    data: () => ({
        dialog: false,
    }),

    methods: {
        onEdit() {
            this.dialog = true
        }
    },

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
