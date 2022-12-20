<template>
  <div class="col-md-6 col-lg-3 mb-5">
    <div class="product">
      <div class="pictSect">
        <img :src="product.picturl" alt=""/>
      </div>
      <div class="text">{{ product.name }}</div>
      <router-link class="nav-link price" :to="{name: 'Product', params: {prod_id: this.product.id}}">
        {{ product.price }} руб.
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: {
    product: {
      type: Object
    }
  }
}
</script>

<style scoped>
.product {
  font-weight: bold;
  position: relative;
  text-align: center;
  border-radius: 10px;
}

.product .price {
  color: #fff;
  width: 100%;
  font-size: xx-large;
  border-bottom-left-radius: 5px;
  border-bottom-right-radius: 5px;
  background-color: rgb(236, 8, 8);
  border: 3px solid #000;
}

.product .text {
  width: 100%;
  color: white;
  padding-top: 2%;
  padding-bottom: 2%;
  background: linear-gradient(rgb(62, 62, 65), rgb(48, 44, 45));
  border-left: 3px solid #000;
  border-right: 3px solid #000;

  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
}

.product .pictSect {
  width: 100%;
  background: white;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  border: 3px solid #000;
}

.product .pictSect img {
  height: 350px;
  position: relative;
  border-radius: 8px;
}
</style>