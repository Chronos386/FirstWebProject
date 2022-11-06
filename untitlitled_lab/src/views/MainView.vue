<template>
  <section>
    <TopMain/>
    <HelloThereBlock/>
    <WhyOurBeerBlock/>
    <ProductsTitleBlock/>
    <ProductsLine v-bind:products="products"/>
    <ThanksBlock/>
    <VideoBlock url="https://www.youtube.com/embed/y8tkWwwql44?autoplay=0&mute=0"/>
  </section>
</template>

<script>
import TopMain from "@/components/TopMain/TopMain"
import HelloThereBlock from "@/components/ContentBlocks/HelloThereBlock"
import WhyOurBeerBlock from "@/components/ContentBlocks/WhyOurBeerBlock"
import ProductsTitleBlock from "@/components/ContentBlocks/ProductsTitleBlock";
import ProductsLine from "@/components/Product/ProductsLine";
import ThanksBlock from "@/components/ContentBlocks/ThanksBlock";
import VideoBlock from "@/components/ContentBlocks/VideoBlock";
export default {
  name: "MainView",
  components: {
    TopMain,
    HelloThereBlock,
    WhyOurBeerBlock,
    ProductsTitleBlock,
    ProductsLine,
    ThanksBlock,
    VideoBlock
  },
  data() {
    return {
      products: [
        {image: "https://sun9-66.userapi.com/impg/kwru8Ld2a0qFvnDlxUMB0zxO7tVfF66N6AqC0A/TY4VtuXpaR0.jpg?size=840x1278&quality=96&sign=5a2271eab47dca66ae5e5bccaa2b8077&type=album",
          title: "Собутыльник (Аянами Рей плюш)", price: "1800"},
        {image: "https://sun9-67.userapi.com/impg/t3YfAJnh0_1HemFygmtDP5uevcdn7SDPEIE8Cg/U_qZychOQQI.jpg?size=840x1278&quality=96&sign=a61ff84a0e4bbc2643ea40203e19603f&type=album",
          title: "Пиво Yebisu (premium, золотое)", price: "990"},
        {image: "https://sun9-24.userapi.com/impg/yG9tuRXsuWTWvgfjCvrJj5XmGYnbRcSwYfj59g/nzUOWSdpHlU.jpg?size=840x1278&quality=96&sign=7ecaf95e4b2b8a9e7bd14a97b101160b&type=album",
          title: "Пиво Yebisu (premium, фиолетовое)", price: "450"},
        {image: "https://sun9-21.userapi.com/impg/rp1KMseeyv_u3i3ZM6IMo521onuictyUJ5-Rcg/lFnSPKHWbaE.jpg?size=840x1278&quality=96&sign=d87f79bcda12f4e7dba468413b0f2525&type=album",
          title: "Пиво Yebisu (premium, зелёное)", price: "550"},

        {image: "https://sun9-17.userapi.com/impg/hxBnJUUKu2Vyekd7Pr62laVDR6iT7NjlZRvZwg/Mj1bZT2eW2I.jpg?size=668x1278&quality=96&sign=c10fe2bd7ee2e3259c31b112210fd052&type=album",
          title: "Пиво Yebisu (premium, белое)", price: "450"},
        {image: "https://sun9-8.userapi.com/impg/2pGG5i22dxcFdRh-DFI_ep_5F0Qepin9Bs2XXA/HkDDWkXYW5w.jpg?size=840x1278&quality=96&sign=c3d1e626bd73d2eacfbe965791bbadc1&type=album",
          title: "Пиво Yebisu (black, фиолетовое)", price: "490"},
        {image: "https://sun9-23.userapi.com/impg/b-Lt2k4WpFzVHaFQ1iK0LZFh1Ptgk2T6HkUGuA/An5Q_TqZATQ.jpg?size=448x1278&quality=96&sign=caa40972bd43d5469fc43070a834c37a&type=album",
          title: "Пиво Kirin Ichiban (first press, bottle)", price: "750"},
        {image: "https://sun9-82.userapi.com/impg/3pe8HZyg7jTWJDHpmG8Ku_K11Hm0l8ZShY_Eew/juD0ZYiowZc.jpg?size=840x1278&quality=96&sign=c799ce127b63aa1a6909e00e0aa69ca6&type=album",
          title: "Пиво Kirin Ichiban", price: "590"},

        {image: "https://sun9-86.userapi.com/impg/3cBeeqvmLYNRzwS6GSgIHVwaC-2SGvWf4DGvsg/z6VR-KC2ZvE.jpg?size=840x1278&quality=96&sign=9b9745ad268734ac20552fc6dd9db280&type=album",
          title: "Пиво Kirin Ichiban (first press, black)", price: "890"},
        {image: "https://sun9-81.userapi.com/impg/roBLk5kT_pHPDofpSm89Iov6M3Xz-fQJddz4Fw/i-SLLPnmxmo.jpg?size=840x1278&quality=96&sign=463886f8a75303e4b39e8d6b555f58e6&type=album",
          title: "Пиво Kirin Ichiban (белое)", price: "490"},
        {image: "https://sun9-68.userapi.com/impg/TJvcarBbmJoYNKHwS-1odL2jf3cvIWyZsBgMnw/FwNt0c1N9eo.jpg?size=840x1278&quality=96&sign=86eb6a277cb5cfe5546c36ce291e1ae8&type=album",
          title: "Упаковка пива Kirin Ichiban (first press)", price: "1590"},
        {image: "https://sun9-65.userapi.com/impg/YLF7yIiTetZ95CVhYWjPj_vHwuNCLjrvOxsEbw/nc7gIxFlCyw.jpg?size=840x1278&quality=96&sign=e308b30ec0261a4ca93456452b0f6850&type=album",
          title: "Пиво Kirin Ichiban (очень светлое)", price: "390"},

        {image: "https://sun9-87.userapi.com/impg/AfdYRpd0l7eQxF3cRwQQ_ItzB0RjDS1LYTGVAQ/ilymVI7jcYo.jpg?size=840x1278&quality=96&sign=ceec90538270eaa461bade9067abdab9&type=album",
          title: "Упаковка пива Kirin Ichiban (светлое)", price: "1990"},
        {image: "https://sun9-72.userapi.com/impg/DLzTtGZ1G9rRROCFzSP5dm5MFif1i3l1EFwUmw/U_1JSZEAdRk.jpg?size=840x1278&quality=96&sign=210ea7511cf3ecd0f4d26f0b4070759f&type=album",
          title: "Пиво Sapporo (premium)", price: "990"}
      ]
    }
  }
}
</script>