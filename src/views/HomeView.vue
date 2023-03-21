<template>
    <div class="home">
        <product-list-one></product-list-one>
        <product-list-two></product-list-two>
    </div>
</template>

<script>
import productListOne from "@/components/ProductListOne";
import productListtwo from "@/components/ProductListTwo";

export default {
    components: {
        "product-list-one": productListOne,
        "product-list-two": productListtwo,
    },
};
</script>
