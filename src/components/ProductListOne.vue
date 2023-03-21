<template>
    <div class="listOne">
        <h1>List Produk 1</h1>
        <ul>
            <li v-for="product in products" :key="product.name">
                <span class="name">{{ product.name }}</span>
                <span class="price">${{ product.price }}</span>
            </li>
        </ul>
        <button @click="reducePrice(4)">reduce</button>
    </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
    computed: {
        products() {
            return this.$store.state.products;
        },
    },
    methods: {
        // reducePrice: function (amount) {
        //     // this.$store.state.products.forEach(product => {
        //     //     product.price -= 1
        //     // })
        //     // this.$store.commit("reducePrice");
        //     this.$store.dispatch("reducePrice", amount);
        // },
        ...mapActions([
            'reducePrice'
        ])
    },
};
</script>

<style scoped>
.listOne {
    background-color: #30c3ec;
    padding: 1rem 0.5rem;
    margin-bottom: 20px;
}
ul {
    display: grid;
    grid-template-columns: 1 1 1 1;
    margin: 0.5rem 0;
}
li {
    list-style-type: none;
    background-color: #e3e5ed;
    border-radius: 16px;
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
