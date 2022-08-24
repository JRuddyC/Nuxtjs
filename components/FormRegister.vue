<template>
  <v-form v-model="valid">
    <v-container
    id="form"
    >
          <v-text-field
            v-model="nombre"
            :rules="nameRules"
            :counter="30"
            label="Nombre del producto"
            required
          ></v-text-field>

          <v-text-field
            v-model="descripcion"
            :rules="nameRules"
            :counter="30"
            label="Descripcion"
            required
          ></v-text-field>
          
          <v-select
          label="Categoria"
          required
        ></v-select>
        <v-text-field
          label="Cantidad"
          value="0"
          type="number"
          prefix="Unidades:"
          required
        ></v-text-field>
        <v-text-field
          label="Precio c/u"
          value="0.00"
          prefix="$"
          type="number"
          required
        ></v-text-field>
        <v-btn
          :disabled="!valid"
          color="success"
          class="mr-4"
          @click="validate"
          >
          Registrar
        </v-btn>
        <v-btn
          color="warning"
          class="mr-4"
          @click="reset"
          >
          Limpiar registro
        </v-btn>
    </v-container>
  </v-form>
</template>
<script>
  export default {
    data: () => ({
      valid: false,
      valid: true,
      nombre: '',
      descripcion: '',
      categoria: '',
      nameRules: [
        v => !!v || 'Dato requerido',
        v => v.length <= 30 || 'El dato debe tener menos de 30 caracteres',
      ]
      
    }),
    methods: {
        validate () {
        this.$refs.form.validate()
      },
      reset () {
        this.$refs.form.reset()
      },
    },
  }
</script>
<style scoped>
#form{
padding-left: 10%;
padding-right: 10%
}
</style>