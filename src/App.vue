<template>
  <div>
    <Header />
    <router-view />
    <Footer />
  </div>
  <!-- <component :is="currentPageComponent" :page-params="currentPageParams"/> -->

</template>

<script>
// import MainPage from './pages/MainPage.vue';
// import ProductPage from './pages/ProductPage.vue';
// import NotFoundPage from './pages/NotFoundPage.vue';
// import eventBus from '@/eventBus';

// const routes = {
//   main: 'MainPage',
//   product: 'ProductPage',
// };
import Header from '@/components/Header.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'App',
  components: { Header, Footer },
  // components: { MainPage, ProductPage, NotFoundPage },
  // data() {
  //   return {
  //     currentPage: 'main',
  //     currentPageParams: {},
  //   };
  // },
  // computed: {
  //   currentPageComponent() {
  //     return routes[this.currentPage] || 'NotFoundPage';
  //   },
  // },
  // methods: {
  //   goToPage(pageName, pageParams) {
  //     this.currentPage = pageName;
  //     this.currentPageParams = pageParams || {};
  //   },
  // },
  // created() {
  //   eventBus.$on('goToPage', (pageName, pageParams) => this.goToPage(pageName, pageParams));
  // },
};
</script>
