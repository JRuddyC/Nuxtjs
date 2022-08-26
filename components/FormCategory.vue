<template>
  <v-form ref="form"
    v-model="valid"
    lazy-validation>
    <v-container
    class="padding"
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
            let datos= this.$refs.form.validate()
            if(datos){
              this.$axios.$post('http://localhost:9000/api/categorias',{
              nombre: this.nombre,
              descripcion: this.descripcion
            })
            .then(res =>{
              console.log(res)
            })
            .catch(error =>{
              console.log(error)
            })
            }
        },
        reset () {
            this.$refs.form.reset()
        },
    },
  }
</script>
<style scoped>
.padding{
padding-left: 10%;
padding-right: 10%
}
</style>