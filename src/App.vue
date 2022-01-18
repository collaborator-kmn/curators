<template>

    <v-app>
        <v-main class="background">
            <v-container>
                <center>
                    <h1>Каталог кураторов клиентов</h1>
                </center>
                <CatalogList v-bind:catalog="catalog"/>
                <CatalogTable v-bind:catalog="catalog"/>
            </v-container>
        </v-main>
    </v-app>
</template>


<script>
import CatalogList from "@/components/CatalogList";
import {Catalog} from "@/entity/Catalog";
import CatalogTable from "@/components/CatalogTable";

export default {
    name: 'App',

    components: {CatalogTable, CatalogList},

    mounted() {
        fetch('http://localhost:8081/catalog')
            .then(response => response.json())
            .then(json => this.catalog = json)
    },

    data: () => ({
        catalog: [
        ]
    }),

    computed:{
        catalogs(){
            return this.catalog.map(result => new Catalog(result))
        }
    }
}
</script>
