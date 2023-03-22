<template>

    <div class="product-items">
        <div class="product-item">
            <img :src="productItem.picture" alt="">

            <div class="product-item-text">

                <h1> <a> {{ productItem.title }} </a></h1>
                <h2><span> {{ productItem.price }}</span>.000đ</h2>
            </div>
            <a class="cartadd" @click="addToCart(productItem)">Thêm vào giỏ hàng</a>
        </div>



    </div>




</template>

<script>
import { mapActions } from "pinia";
import { useCartStore } from "@/stores/cart";


export default {
    name: "ProductListItem",
    props: ["productItem"],


    methods: {
        ...mapActions(useCartStore, ["addToCart"]),
    },
};
</script>

<style scoped>

.product-item-text h1 {
    font-family: Arial, Helvetica;
    font-size: 15px;
    color: #666;
}

.product-item-text h2 {
    font-family: Arial, Helvetica, sans-serif;
    color: #ed1c24;
    font-size: 16px;
    display: block;


}

.product-items {
    display: inline-block;
    width: 250px;
    height: 280px;
    padding: 0px;
    margin-bottom: 10px;

}

.product-item {
    display: inline-block;
    background: #fff;
    padding: 12px;
    text-align: center;

    box-sizing: border-box;
    margin-bottom: 25px;
    box-shadow: 1px 3px 3px 0px #0000001a;
    border-radius: 5px;
    transition: transform linear 0.1s;
    will-change: transform;
    margin-right: 5px;
    height: 315px;
}

.product-item img {
    width: 80%;
    margin-bottom: 10px;
}

.product-item-text {

    display: block;
}

/* .product-item #cartadd{
       margin-top: 12px;
       height: 30px;
       padding: 0 8px;
       cursor: pointer;
       border: none;
      

   } */

.product-item .cartadd {
    text-decoration: none;
    text-transform: uppercase;
    text-align: center;
    /* display: block; */
    cursor: pointer;

    color: #fff;
    padding: 10px 0px;
    position: absolute;
    width: 100%;
    bottom: 46px;
    transition: 0.25s ease-in-out;
    border: none;
    opacity: 80%;


}

.product-item:hover>.cartadd {
    bottom: 50px;
    background-color: #ED1C24;
    right: 0;
    left: 0;
}

ion-icon {
    font-size: 22px;
}
</style>
