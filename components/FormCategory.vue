<template>
  <v-form ref="form"
    v-model="valid"
    lazy-validation>
    <v-container
    id="form"
    >
          <v-text-field
            v-model="nombre"
            :rules="nameRules"
            :counter="30"
            label="Nombre de categoria"
            required
          ></v-text-field>

          <v-text-field
            v-model="descripcion"
            :rules="nameRules"
            :counter="30"
            label="Descripcion de categoria"
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

      valid: true,
      nombre: '',
      descripcion: '',
      nameRules: [
        v => !!v || 'Dato requerido'
        //v => v.length <= 30 || 'El dato debe tener menos de 30 caracteres',
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