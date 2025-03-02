<template>
  <q-page padding>
    <q-form>
      <div class="q-mb-md">
          <q-input v-model="name" label="Nome" outlined/>
      </div>
      <div class="row" q-col-gutter-x-md>
        <q-input class="col-8" v-model="bornDate" label="Data de Nascimento" outlined>
          <template v-slot:append>
            <q-icon name="event" class="cursor-point">
              <q-popup-proxy>
                <q-date model-value=""/>
              </q-popup-proxy>
            </q-icon>
          </template>
        </q-input>
        <q-select class="col-4" v-model="gender"
                  label="Gênero"
                  outlined
                  :options="[
                  'Masculino',
                  'Feminino',
                  ]"
        />
      </div>
      <div class="column">
        <q-checkbox v-model="term" label="Aceito os termos de uso!" />
        <q-btn label="Salvar" color="primary"/>
      </div>
    </q-form>
  </q-page>
</template>

<script lang="ts">

import { defineComponent, ref } from 'vue'

export default defineComponent (  {
    name: 'UserPage',
    setup () {
      const name = ref<string> ('')
      const bornDate = ref<string> ('')
      const gender = ref<string> ('')
      const term = ref<boolean> (false)


      return {
        name,
        bornDate,
        gender,
        term
    }
  }
} )

</script>

<style lang = "scss" scoped>
  .my-class {
  color: red;
}
</style>
