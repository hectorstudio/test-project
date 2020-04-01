<template>
  <div class="related-resources">
    <div class="resource-title">
      Related Resources
    </div>
    <div class="resource-items">
      <VueSlickCarousel v-bind="settings">
        <RelatedItem v-for="(item, index) in resources" :key="index" :resource="item" />
      </VueSlickCarousel>
    </div>
  </div>
</template>

<script>
  import VueSlickCarousel from 'vue-slick-carousel'
  import 'vue-slick-carousel/dist/vue-slick-carousel.css'
  // optional style for arrows & dots
  import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'

import RelatedItem from "../components/RelatedItem.vue";

export default {
  name: "RelatedResources",
  components: {
    VueSlickCarousel,
    RelatedItem
  },
  props:{
    resources: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      settings: {
        arrows: false,
        dots: false,
        // centerPadding: "20px",
        // focusOnSelect: true,
        // infinite: true,
        slidesToShow: 2,
      }
    }
  },
  mounted() {
    console.log(this.resources);
  }
};
</script>

<style lang="scss">
$regular: 400;
$normal: 500;
$semi-bold: 600;
$bold: 700;

.related-resources {
  border-bottom: 1px solid #605f5f;
  .resource-title {
    padding: 20px 0px 10px 10px;
    font-family: Raleway, sans-serif;
    color: #ffffff;
    font-weight: $bold;
    font-size: 18px;
  }
  .resource-items {
  }
}
</style>
