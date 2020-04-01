<template>
  <button v-bind:class="['btn', size, color, transform, active, height]">
    <i v-bind:class="[icon]"></i> {{ buttonName }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    size: String,
    color: String,
    transform: String,
    active: String,
    icon: String,
    buttonName: String,
    height: String,
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">

$regular: 400;
$normal: 500;
$semi-bold: 600;
$bold: 700;

.btn {
  font-family: Raleway, sans-serif;
  background: transparent;
  border: none;
  outline: none;
  color: #ffffff;
  display: flex;
  background-color: #2e2828;
  justify-content: baseline;
  align-items: center;
  border-radius: 5px;
  &.btn-small {
    font-size: 14px;
    font-weight: $regular;
    padding: 10px 11px;
  }
  &.height-fit {
    height: fit-content;
  }
  &.btn-medium {
    font-weight: $normal;
    padding: 10px 23.5px;
    font-size: 14px;
    margin-right: 10px;
    line-height: 16px;
    color: #605f5f;
    border: 1px solid #362f2f;
    box-sizing: border-box;
  }
  &.active {
    background: #362f2f;
  }
  &.btn-large {
    font-weight: $semi-bold;
    padding: 18px 15px;
    min-width: 105px;
    font-size: 19px;
  }
  &.primary {
    color: #ffffff;
    justify-content: center;
    background: #7f00ec;
  }
  &.uppercase {
    text-transform: uppercase;
  }
}
</style>
