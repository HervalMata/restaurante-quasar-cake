<template>
  <q-layout view="hHr Lpr lfr">
    <q-layout-header>
      <q-toolbar
        color="green"
      >
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
        >
          <q-icon name="menu" />
        </q-btn>

        <q-toolbar-title>
          Quasar App
          <div slot="subtitle">Running on Quasar v{{ $q.version }}</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-layout-header>

    <q-layout-drawer
      v-model="leftDrawerOpen"
      content-class="bg-amber-3"
      id="sidebar"
    >
      <q-list
        no-border
        link
        inset-delimiter
      >
        <q-item>
          <img src="~assets/logo.png" alt="">
        </q-item>
        <q-list-header>O que você quer fazer</q-list-header>
        <q-item to="">
          <q-item-side icon="search" />
          <q-item-main label="Quero pedir" sublabel="Busque por restaurantes e faça um pedido" />
        </q-item>
        <q-item to="">
          <q-item-side icon="fastfood" />
          <q-item-main label="Tenho um restaurante"
                       sublabel="Cadastre um restaurante e receba seus pedidos" />
        </q-item>
        <q-item to="">
          <q-item-side icon="shopping_cart" />
          <q-item-main label="Meus Pedidos" sublabel="Acompanhe seus últimos pedidos" />
        </q-item>
        <q-item to="">
          <q-item-side icon="account_box" />
          <q-item-main label="Entrar" sublabel="Acesse sua conta" />
        </q-item>
      </q-list>
    </q-layout-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { openURL } from 'quasar';

export default {
  name: 'MyLayout',
  data() {
    return {
      leftDrawerOpen: this.$q.platform.is.desktop,
    };
  },
  methods: {
    openURL,
  },
};
</script>

<style>
  #sidebar .q-item.router-link-active {
    background: rgba(0, 0, 0, 0.1);
  }
  #sidebar .q-item.router-link-active:hover {
    background: rgba(0, 0, 0, 0.3);
  }
  #sidebar .q-item img {
    width: 94%;
    height: 120px;
    padding: 3% 0;
  }
</style>
