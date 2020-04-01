<template>
  <div class="resource-item">
    <div class="ribbon">$30</div>
    <div class="item-title">
      Top 10 Virtual Museums
    </div>
    <div class="item-detail">
      Check out the best museums that are now streaming online
    </div>
  </div>
</template>

<script>
export default {
  name: "RelatedItem",
  props: {
    resource: {
      type: Object,
      required: true
    }
  },
  mounted() {
    console.log(this.resource);
  }
};
</script>

<style lang="scss">
$regular: 400;
$normal: 500;
$semi-bold: 600;
$bold: 700;
$ribbonColor: #7f00ec;

.resource-item {
  max-width: 200px;
  margin: 0px 10px 10px 10px;
  padding: 30px 20px;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25), 0px 4px 4px rgba(0, 0, 0, 0.25);
  .item-title {
    width: 70%;
    font-family: Raleway, sans-serif;
    color: #ffffff;
    font-weight: $bold;
    font-size: 16px;
  }
  .item-detail {
    width: 85%;
    margin-top: 10px;
    font-family: Raleway, sans-serif;
    color: #605f5f;
    font-weight: $regular;
    font-size: 14px;
  }
  .ribbon {
    width: 40px;
    height: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: -30px;
    margin-left: 8.5%;
    color: #ffffff;
    font-family: Raleway, sans-serif;
    font-size: 14px;
    background-color: $ribbonColor;
    position: absolute;
    animation: drop forwards 0.8s 1s cubic-bezier(0.165, 0.84, 0.44, 1);
    &:before {
      content: "";
      position: absolute;
      z-index: 2;
      left: 0;
      bottom: -7px;
      border-left: 20px solid $ribbonColor;
      border-right: 20px solid $ribbonColor;
      border-bottom: 7px solid transparent;
    }
  }
}
</style>
