<template>
<v-container
>
    <v-card
    elevation="24"
    outlined
    shaped
    id="form"
    >
    <v-card-title>
        REGISTRO DE PRODUCTOS
        </v-card-title>
        <form-register/>
    </v-card>
</v-container>
</template>
<script>
export default{
    name: 'RegisterPage'
}
</script>
<style scoped>
.v-card__title{
    justify-content: center;
}
#form{
    margin-left: 10%;
    margin-right: 10%;
    width: 600px;
    min-width:450px;
}
.container{
    display: flex;
    justify-content: center;
}
</style>