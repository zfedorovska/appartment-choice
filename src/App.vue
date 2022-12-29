<template>
  <div :id="$style.app">
  <AppartmentsList
  :items="appartments"
  />
  </div>
</template>

<script>
import AppartmentsList from './components/appartment/AppartmentsList.vue';
import appartments from './components/appartment/apartments'

export default {
  name: 'App',
  components: {
    AppartmentsList,
  },
  data() {
    console.log(appartments);
    return {
      appartments,
      appartment: {
        id: '3333444',
        title: 'Good Place',
        descr: 'Where you can forget about yourself',
        price: 2032,
        location: {
          city: 'Kostopil',
        },
        owner: {
          name: 'Zoryana',
          phone: '222-2222-22222',
          email: 'zfedorovska@gmail.com'
        },
        rating: 4,
      }
    }
  },
  computed: {
  },
  methods: {
  }
}
</script>

<style module>
#app {
  font-family: Montserrat, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
