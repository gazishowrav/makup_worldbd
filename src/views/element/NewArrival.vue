<template>
    <div class="products">
      <!--New Arrival-->
						<div class="new-arrival">
							<div class="row">
								<div class="col-lg-6">
									<h2 class="title mb-0">New Arrival Item</h2>
								</div>
								<div class="col-lg-6">
									<ul class="nav justify-content-end" id="myTab" role="tablist">
									  <li class="nav-item">
									    <a class="nav-link active" id="featured-tab" data-toggle="tab" href="#featured" role="tab" aria-controls="featured" aria-selected="true">Featured</a>
									  </li>
									  <li class="nav-item">
									    <a class="nav-link" id="bestSeller-tab" data-toggle="tab" href="#bestSeller" role="tab" aria-controls="bestSeller" aria-selected="false">Best Seller</a>
									  </li>
									</ul>
								</div>
								<div class="col-lg-12">
									<hr>
								</div>
							</div>
							<div class="tab-content" id="myTabContent">
							  <div v-if="owlSlide.length > 0" class="tab-pane fade show active" id="featured" role="tabpanel" aria-labelledby="featured-tab">
							  	<section v-if="errored">
                    <p>We're sorry, we're not able to retrieve this information at the moment, please try back later</p>
                  </section>
                  <section v-else>
                  <div v-if="loading">Loading...</div>
                    <carousel class="featured" :autoplay="true" :dots="false" :items="4">
                      <div class="item" v-for="(item, index) in owlSlide" :key="index">
                        <div class="card card-body d-block">
                          <router-link to="/" class="img-box">
                            <img :src="item.product_image.name" :alt="item.product_image.name">
                          </router-link>
                          <ul class="nav rating">
                            <li><i class="mdi mdi-star"></i></li>
                            <li><i class="mdi mdi-star"></i></li>
                            <li><i class="mdi mdi-star"></i></li>
                            <li><i class="mdi mdi-star"></i></li>
                            <li><i class="mdi mdi-star"></i></li>
                          </ul>
                          <a href="product-details.html">
                            <h3>{{item.name}}</h3>
                          </a>
                          <div class="position-relative">
                            <div class="price-box">
                              <span class="offer-price">৳{{item.discount}}</span>
                              <span class="recent-price">৳{{item.sell_price}}</span>
                            </div>
                            <div class="addcart-box">
                              <a href="#"><i class="mdi mdi-cart"></i></a>
                              <a href="#"><i class="mdi mdi-heart"></i></a>
                              <a href="product-details.html"><i class="mdi mdi-eye"></i></a>
                              <a href="#"><i class="mdi mdi-content-copy"></i></a>
                            </div>
                          </div>
                        </div>
                      </div>
                    </carousel>
                  </section>
							  </div>
							  <div v-if="owlSlide.length > 0" class="tab-pane fade" id="bestSeller" role="tabpanel" aria-labelledby="bestSeller-tab">
                  <section v-if="errored">
                    <p>We're sorry, we're not able to retrieve this information at the moment, please try back later</p>
                  </section>
                  <section v-else>
                  <div v-if="loading">Loading...</div>
                    <carousel class="featured" :autoplay="true" :dots="false" :items="4">
                      <div class="item" v-for="(item, index) in owlSlide" :key="index">
                        <div class="card card-body d-block">
                          <router-link to="/" class="img-box">
                            <img :src="item.product_image.name" :alt="item.product_image.name">
                          </router-link>
                          <ul class="nav rating">
                            <li><i class="mdi mdi-star"></i></li>
                            <li><i class="mdi mdi-star"></i></li>
                            <li><i class="mdi mdi-star"></i></li>
                            <li><i class="mdi mdi-star"></i></li>
                            <li><i class="mdi mdi-star"></i></li>
                          </ul>
                          <a href="product-details.html">
                            <h3>{{item.name}}</h3>
                          </a>
                          <div class="position-relative">
                            <div class="price-box">
                              <span class="offer-price">৳{{item.discount}}</span>
                              <span class="recent-price">৳{{item.sell_price}}</span>
                            </div>
                            <div class="addcart-box">
                              <a href="#"><i class="mdi mdi-cart"></i></a>
                              <a href="#"><i class="mdi mdi-heart"></i></a>
                              <a href="product-details.html"><i class="mdi mdi-eye"></i></a>
                              <a href="#"><i class="mdi mdi-content-copy"></i></a>
                            </div>
                          </div>
                        </div>
                      </div>
                    </carousel>
                  </section>
                </div>
							</div>
						</div>
						<!--/New Arrival-->
            <pre>{{owlSlide}}</pre>
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
        info: [],
        owlSlide: [],
        loading: true,
        errored: false 
      }
    },
    mounted () {
      this.$http.get('http://mwbddemo.com/makeup/api/products')
      .then(response => {
          this.info = response.data
          this.owlSlide = response.data.productsList.data
      })
      .catch(error => {
          console.log(error)
          this.errored = true
      })
      .finally(() => this.loading = false)
    }
   }
</script>

<style>

</style>