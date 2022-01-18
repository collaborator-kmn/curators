<template>
    <li>
        {{item}}
    </li>
</template>

<script>
    export default {
        props:{
            item:{
                type: Object,
                required:true
            }
        }
    }
</script>

<style scoped>
</style>
