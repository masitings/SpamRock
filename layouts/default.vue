<template>
  <div>
    <AppHeader />
    <nuxt />
  </div>
</template>

<script>
import AppHeader from '../components/AppHeader';

export default {
  components: {
    AppHeader
  }
}
</script>
<style>
  body{
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.6;
  }
</style>