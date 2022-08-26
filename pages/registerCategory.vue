<template>
<v-container
class = 'd-flex justify-center'
>
    <v-card
    elevation="24"
    outlined
    shaped
    id="form"
    min-width = "450px"
    width = "600px" 
    class="margin"
    >
        <v-card-title
        class="d-flex justify-center"
        >
        REGISTRO DE CATEGORIAS
        </v-card-title>
        <form-category/>
    </v-card>
</v-container>
</template>
<script>
export default{
    name: 'RegisterPage'
}
</script>
<style scoped>
.margin{
    margin-left: 10%;
    margin-right: 10%
}
</style>