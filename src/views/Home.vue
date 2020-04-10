<template>
  <div class="home">
    <Header/>
    <!-- main-->
    <main class="main">
      <Slider/>
      <!--products view-->
      <div class="products-view pt-5">
        <div class="container-wrapper">
          <div class="row">
            <div class="col-lg-3"></div>
            <div class="col-lg-9">
              <Depertment/>
              <DoubleFutureCard/>
              <NewArrival/>
            </div>
          </div>
        </div>
      </div>
      <!--/products view-->
    </main>
    <!-- /main-->
    <Footer/>
    <AddToCard/>
  </div>
</template>

<script>
import NewArrivalVue from './element/NewArrival.vue'
// @ is an alias to /src
export default {
  name: 'Home',
  components: {
    AddToCard: () => import(/* webpackChunkName: "AddToCard" */ "@/components/AddToCard"),
    Header: () => import(/* webpackChunkName: "Header" */ "@/components/Header"),
    Footer: () => import(/* webpackChunkName: "Footer" */ "@/components/Footer"),
    Slider: () => import(/* webpackChunkName: "Slider" */ "./element/Slider"),
    Depertment: () => import(/* webpackChunkName: "Depertment" */ "./element/Depertment"),
    DoubleFutureCard: () => import(/* webpackChunkName: "DoubleFutureCard" */ "./element/DoubleFutureCard"),
    NewArrival: () => import(/* webpackChunkName: "NewArrival" */ "./element/NewArrival")
  }
}
</script>
