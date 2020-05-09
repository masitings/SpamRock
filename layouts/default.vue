<template>
  <div>
    <AppHeader />
      <nuxt />
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from '../components/AppHeader';
import AppFooter from '../components/AppFooter';

export default {
  components: {
    AppHeader,
    AppFooter
  }
}
</script>
<style>
  body{
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.6;
  }
</style>