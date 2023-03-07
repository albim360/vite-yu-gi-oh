<template>
  <div id="app">
    <AppHeader @search="filter = $event" />
    <AppMain :filter="filter" />
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },
  data() {
    return {
      filter: '',
    };
  },
};
</script>
