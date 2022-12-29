<template>
    <Container>
        <div class="apartments-list">
            <AppartmentsItem 
            v-for="{id, descr, rating, imgUrl, price} in items"
            :key="id" 
            :descr="descr"
            :rating="rating"
            :imgSrc="imgUrl"
            :price="price"/>
        </div>
        </Container>
</template>

<script>
import AppartmentsItem from './AppartmentsItem'
import Container from '../shared/Container.vue'

export default {
    name: 'ApartmentsList',
    components: {
        AppartmentsItem,
        Container
    },
    props: {
        items: {
            type: Array,
            default: () => [],
        },
    },
}
</script>

<style lang="scss" scoped>
.apartments-list {
    display: flex;
    flex-wrap: wrap;
    margin-left: -15px;
    margin-right: -15px;
}
</style>