<template>
  <div class="resource-item">
    <div class="item-title">
      {{title}}
    </div>
    <div class="item-detail">
      {{detail}}
    </div>
  </div>
</template>

<script>

export default {
  name: "RelatedItem",
  props: {
    title: String,
    detail: String,
  }
};
</script>

<style lang="scss">
$regular: 400;
$normal: 500;
$semi-bold: 600;
$bold: 700;
.resource-item {
  max-width: 200px;
  margin: 0px 10px 10px 10px;
  padding: 30px 20px;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25),
    0px 4px 4px rgba(0, 0, 0, 0.25);
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
}
</style>
