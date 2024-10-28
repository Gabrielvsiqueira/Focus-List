<template>
  <PageHeader></PageHeader>
  <HomePage></HomePage>
</template>

<script>
import PageHeader from './components/PageHeader.vue';
import HomePage from './components/HomePage.vue';

export default {
  name: 'App',
  components: {
    HomePage,
    PageHeader
  }
}
</script>

<style>
*{
  margin: auto;
  background-color: #237d39;
  font-family: 'poppins';
  color: #FFFF;
}
</style>
