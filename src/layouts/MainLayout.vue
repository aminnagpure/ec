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
      images: [
        'https://images-na.ssl-images-amazon.com/images/I/81Vv9UvptRL._SY355_.png',
        'https://images-na.ssl-images-amazon.com/images/I/81B8zxdRaRL._SY355_.png',
        'https://images-na.ssl-images-amazon.com/images/I/71zFKb2gQNL._SX425_.png',
        'https://images-na.ssl-images-amazon.com/images/I/41a1syPyhOL.jpg',
        'https://n2.sdlcdn.com/imgs/e/i/7/Ritzkart-Brown-Formal-Hair-Wig-SDL063790351-2-affc0.JPG',
        'https://www.thehindu.com/entertainment/movies/o50yp7/article31455525.ece/alternates/FREE_435/thappad',
        'https://images-eu.ssl-images-amazon.com/images/I/615mQ9fY6bL.jpg',
        'https://mcdn.wallpapersafari.com/medium/23/62/714DV3.jpg',
        'https://images-na.ssl-images-amazon.com/images/I/81B8zxdRaRL._SY355_.png',
        'https://images-na.ssl-images-amazon.com/images/I/41a1syPyhOL.jpg',
        'https://www.thehindu.com/entertainment/movies/o50yp7/article31455525.ece/alternates/FREE_435/thappad',
        'https://n2.sdlcdn.com/imgs/e/i/7/Ritzkart-Brown-Formal-Hair-Wig-SDL063790351-2-affc0.JPG',
      ],
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
