<template>
    <div class="listTwo">
        <h1>List Produk 2</h1>
        <ul>
            <li v-for="product in saleProducts" :key="product.name">
                <span>{{ product.name }}</span>
                <span>${{ product.price }}</span>
            </li>
        </ul>
    </div>
</template>

<script>
import { mapGetters } from 'vuex';
export default {
    computed: {
        products() {
            return this.$store.state.products;
        },
       
        ...mapGetters([
            'saleProducts'
        ])
    },
};
</script>
<style scoped>
.listTwo {
    background-color: #ccd5ae;
    padding: 1rem 0.5rem;
}
ul {
    display: grid;
    grid-template-columns: 1 1 1 1;
    margin: 0.5rem 0;
}
li {
    list-style-type: none;
    background-color: #dbdbdb;
    border-radius: 0 25px 0 25px;
    box-shadow: 2px 4px rgba(0, 0, 0, 0.2);
    margin: 1rem 0.5rem;
    padding: 2em 0.5rem;
}
.price {
    margin-left: 0.5em;
    color: #c12b1e;
    font-weight: bold;
}

@media only screen and (min-width: 768px) {
    /* For desktop: */
    ul {
        grid-template-columns: auto auto;
    }
}

@media only screen and (min-width: 992px) {
    ul {
        grid-template-columns: auto auto auto auto;
    }
}
</style>
