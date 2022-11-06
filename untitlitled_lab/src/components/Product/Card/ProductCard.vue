<template>
  <div class="col-md-6 col-lg-3 mb-5">
    <div class="product">
      <div class="pictSect">
        <img :src="product.image" alt=""/>
      </div>
      <div class="text">{{ product.title }}</div>
      <router-link class="nav-link" :to="{name: 'Product', params: {price: product.price, name: product.title,
      count: count, characteristics: characteristics, image: product.image}}">
        <button class="price" >{{ product.price }} руб.</button>
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
  },
  data() {
    return {
      characteristics: [
        {title: "Brand:", item: "Great Eastern"},
        {title: "Theme:", item: "Movie"},
        {title: "Toy figure type:", item: "Stuffed Toy"},
        {title: "Color:", item: "Multi-colored"},
        {title: "Material:", item: "Polyester"},
        {title: "Cartoon Character:", item: "Rei"},
        {title: "•", item: "Official product by Great Eastern"},
        {title: "•", item: "Cute and collectible"},
        {title: "•", item: "Makes a great gift"},
        {title: "•", item: "Limited availability"},
        {title: "•", item: "Approx. Size: 4.5\"L x 3\"W x 8\"H"}
      ],
      count: "999"
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
    border: 3px solid #000;
  }

  .product .price {
    color: #fff;
    width: 100%;
    font-size: xx-large;
    border-bottom-left-radius: 5px;
    border-bottom-right-radius: 5px;
    background-color: rgb(236, 8, 8);
  }

  .product .text {
    width: 100%;
    color: white;
    padding-top: 2%;
    padding-bottom: 2%;
    background: linear-gradient(rgb(62, 62, 65), rgb(48, 44, 45));
  }

  .product .pictSect {
    width: 100%;
    background: white;
    border-top-left-radius: 5px;
    border-top-right-radius: 5px;
  }

  .product .pictSect img {
    height: 350px;
    border-radius: 8px;
  }
</style>