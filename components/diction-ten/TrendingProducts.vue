<template>
    <div>
        <div class="popular-products-area pb-60">
            <div class="container">
                <div class="products-category-tab-style-2">
                    <div class="title">
                        <h2><span class="dot"></span> Trending Products</h2>
                    </div>
                    <b-tabs content-class="mt-3 tab_content">
                        <b-tab title="All">
                            <div class="tabs_item">
                                <div class="row">
                                    <SpecialOfferItem
                                        v-for="(product, index) in products"
                                        :product="product"
                                        :key="index"
                                        @clicked="toggle"
                                        :className="`col-lg-4 col-md-6 col-sm-6`"
                                    ></SpecialOfferItem>
                                </div>
                            </div>
                        </b-tab>

                        <b-tab title="Men">
                            <TabMenProducts />
                        </b-tab>

                        <b-tab title="Women">
                            <div class="tabs_item">
                                <div class="row">
                                    <SpecialOfferItem
                                        v-for="(product, index) in products"
                                        :product="product"
                                        :key="index"
                                        @clicked="toggle"
                                        :className="`col-lg-4 col-md-6 col-sm-6`"
                                    ></SpecialOfferItem>
                                </div>
                            </div>
                        </b-tab>
                    </b-tabs>
                </div>
            </div>
        </div>
        <QuckView />
    </div>
</template>

<script>
import QuckView from '../modals/QuckView'
import { mutations } from '../../utils/sidebar-util'
import SpecialOfferItem from '../common/SpecialOfferItem'
import TabMenProducts from '../diction-ten/TabMenProducts'

export default {
    name: 'TrendingProducts',
    components: {
        QuckView,
        SpecialOfferItem,
        TabMenProducts
    },
    methods: {
        toggle() {
            mutations.toggleQuickView()
        },
    },
    computed: {
        products() {
            return this.$store.state.products.all.filter(
                (product) => product.specialTwo === true
            )
        },
    },
}
</script>