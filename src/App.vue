<template>

    <v-app>
        <v-main class="background">
            <v-container>
                <center>
                    <h1>Каталог кураторов клиентов</h1>
                </center>
                <CatalogTable v-bind:catalog="catalog"/>
            </v-container>
        </v-main>
    </v-app>
</template>


<script>
import {Catalog} from "@/entity/Catalog";
import CatalogTable from "@/components/CatalogTable";

export default {
    name: 'App',

    components: {CatalogTable},

    // mounted() {
    //     fetch('http://localhost:8081/catalog')
    //         .then(response => response.json())
    //         .then(json => this.catalog = json)
    // },

    data: () => ({
        catalog: [
            {
                arm: "internal_arm_1", boss: "internal_boss_1", curators: [
                    "curator_1", "curator_2"
                ]
            },
            {
                arm: "internal_arm_2", boss: "internal_boss_2", curators: [
                    "curator_4", "curator_3"
                ]
            }
        ]
    }),

    computed: {
        catalogs() {
            return this.catalog.map(result => new Catalog(result))
        }
    }
}
</script>
