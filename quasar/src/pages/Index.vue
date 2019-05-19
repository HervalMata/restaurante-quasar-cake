<template>
  <q-page padding>
    <div class="flex flex-center">
      <h1 class="q-display-3">Voce quer comer o que?</h1>
    </div>
    <div class="row gutter-md">
      <div class="col-xs-12 col-md-4">
        <q-card color="primary">
          <q-card-title>
            Usar minha localização atual
          </q-card-title>
          <q-card-separator/>
          <q-card-main>
            Próximo de ...
          </q-card-main>
          <q-card-actions>
            <q-btn to="/list-restaurants" label="Ver restaurantes" color="green"/>
          </q-card-actions>
        </q-card>
      </div>
      <div class="col-xs-12 col-md-4">
        <q-card color="orange">
          <q-card-title>
            Acessar sua conta
          </q-card-title>
          <q-card-separator/>
          <q-card-main>
            Você pode pedir usando uma conta existente acesse
            sua conta para começar
          </q-card-main>
          <q-card-actions>
            <q-btn to="/list-restaurants" label="Acessar conta" color="green"/>
          </q-card-actions>
        </q-card>
      </div>
      <div class="col-xs-12 col-md-4">
        <q-card color="indigo">
          <q-card-title>
            Escolher uma localização
          </q-card-title>
          <q-card-separator/>
          <q-card-main>
            <q-btn
              color="white"
              text-color="primary"
              size="md"
              class="q-ma-md q-mb-md"
              :label="place"
              v-for="(place, index) in places"
              :key="index"
            />
          </q-card-main>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<style>
</style>

<script>
export default {
  name: 'PageIndex',
  data() {
    return {
      places: [
        'CIDADE 1',
        'CIDADE 2',
        'BAIRRO 1',
        'BAIRRO 2',
        'CIDADE 3',
      ],
    };
  },
};
</script>
