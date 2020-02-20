<template>
  <v-app>
    <v-content>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>


<script>
import Vue from 'vue';
import VueRouter from 'vue-router'

import ListView from '../components/ListViewComponent';


const Foo = { template: '<div>foo</div>' }

const routes = [
  { path: '/foo', component: Foo },
  { path: '/', component: ListView }
]
const router = new VueRouter({
  routes // short for `routes: routes`
})

export default {
  name: 'HomeLayout',
  router,
  components: {
  },

  data: () => ({
    //
  }),
};
Vue.use(VueRouter);
</script>