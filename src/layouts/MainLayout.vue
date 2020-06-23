<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

        <q-toolbar-title>
          Play Boys Near You
        </q-toolbar-title>

        <div>
          <q-btn type="primary" :label=label v-on:click="login"/>
        </div>

      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Contact By City
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <q-page padding>
      <router-view />
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script>
import "assets/tem.css";
import EssentialLink from 'components/EssentialLink.vue'
web3 = window.web3;

export default {
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  data () {
    return {
      label:"Login with MetaMask",
      leftDrawerOpen: false,
      essentialLinks: [
        {
          title: 'Delhi',
          caption: 'quasar.dev',
          icon: 'school',
          link: 'https://quasar.dev'
        },
        {
          title: 'Mumbai',
          caption: 'github.com/quasarframework',
          icon: 'code',
          link: 'https://github.com/quasarframework'
        }
      ]
    }},methods:{

login(){
  alert("wer")
web3 = new Web3(web3.currentProvider);
        window.web3 = new Web3(web3.currentProvider);
       this.label=window.web3.currentProvider.selectedAddress;
       alert(window.web3.currentProvider.selectedAddress)
    	console.log(web3.currentProvider);
  
}
    }}
    

</script>
