<template>
  <div :id="$style.app">
      <h2>{{ text }}</h2>
      <ApartmentsFilterForm
        class="apartments-filter"
        @submit="logger"/>
      <ApartmentsList
  :items="apartments"
  >
  <template v-slot:apartment="{ apartment }">
 
      <ApartmentsItem 
        :key="apartment.id" 
        :descr="apartment.descr" 
        :rating="apartment.rating" 
        :imgSrc="apartment.imgUrl"
        :price="apartment.price" />
  </template>
</ApartmentsList>
  </div>
</template>

<script>
import ApartmentsList from './components/apartment/ApartmentsList.vue';
import ApartmentsItem from './components/apartment/ApartmentsItem.vue';
import apartments from './components/apartment/apartments';
import ApartmentsFilterForm from './components/apartment/ApartmentsFilterForm.vue';


export default {
  name: 'App',
  components: {
    ApartmentsList,
    ApartmentsItem,
    ApartmentsFilterForm
  },
  data() {
    return {
      text: '',
      apartments,
    }
  },
  computed: {
  },
  methods: {
    logger(value) {
      console.log(value, 'form value');
    }
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
