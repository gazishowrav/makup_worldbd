<template>
  <div class="depertment">
        <!--shop by depertment-->
        <div class="shop-by-catagory mb-3">
            <div class="shop-by-catagory-body">
                <h3>Shop By Department <span>Choose What You Looking For</span></h3>
                <carousel class="depertment" :autoplay="false"
          :dots="false"
          :nav="false"
          :margin="15"
          :responsive="{0:{items:1},600:{items:2}}">
                    <div class="item" v-for="(item, index) in depertment" :key="index">
                        <a href="products.html" class="card">
                            <div class="card-header">
                                <img :src="item.url" :alt="item.name">
                            </div>
                            <div class="card-body text-center">
                                {{item.name}}
                            </div>
                        </a>
                    </div>
                </carousel>
            </div>
        </div>
        <!--/shop by depertment-->
  </div>
</template>

<script>
import carousel from 'vue-owl-carousel'
export default {
    components: {
        carousel
    },
    data() {
        return {
            depertment: [
                {
                    url: require('../../assets/img/shop-by-depertment/cat-2-130x130_t.jpg'),
                    name: "Accessories"
                },
                {
                    url: require('../../assets/img/shop-by-depertment/cat-3-130x130_t.jpg'),
                    name: "Induction"
                },
                {
                    url: require('../../assets/img/shop-by-depertment/cat-4-130x130_t.jpg'),
                    name: "Camera"
                },
                {
                    url: require('../../assets/img/shop-by-depertment/cat-5-130x130_t.jpg'),
                    name: "Headphone"
                },
                {
                    url: require('../../assets/img/shop-by-depertment/cat-6-130x130_t.jpg'),
                    name: "Shorts"
                },
                {
                    url: require('../../assets/img/shop-by-depertment/cat-7-130x130_t.jpg'),
                    name: "Bags"
                },
                {
                    url: require('../../assets/img/shop-by-depertment/cat-1-130x130_t.jpg'),
                    name: "Shows"
                },
            ]
        }
    }
}
</script>

<style>

</style>