<template>
  <div>
    <TopHeader />
    <Menubar />
    <!-- Start Page Title Area -->
    <div class="page-title-area">
      <div class="container">
        <ul>
          <li><nuxt-link to="/">Home</nuxt-link></li>
          <li>All Products</li>
        </ul>
      </div>
    </div>
    <!-- End Page Title Area -->

    <!-- Start Collections Area -->
    <div class="products-collections-area ptb-60">
      <div class="container">
        <div class="section-title">
          <h2><span class="dot"></span> Products</h2>
        </div>

        <div class="row">
          <Sidebar />
          <AllProducts />
        </div>
      </div>
    </div>
    <!-- End Collections Area -->
  </div>
</template>

<script>
import TopHeader from '../layouts/TopHeader'
import Menubar from '../layouts/Menubar'
import Sidebar from '../components/all-products/Sidebar'
import AllProducts from '../components/all-products/AllProducts'

export default {
  components: {
    TopHeader,
    Menubar,
    Sidebar,
    AllProducts,
  },
}
</script>