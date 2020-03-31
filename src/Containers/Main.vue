<template>
  <div class="application-body">
    <div class="app-header">
      <div class="search-container">
        <form class="search-form">
          <i class="fa fa-search"></i>
          <input type="text" name="search_value" placeholder="Search..." />
        </form>
      </div>
      <div class="auth-btn-group">
        <Button size="btn-large" buttonName="Login" />
        <Button
          size="btn-large"
          color="primary"
          transform="uppercase"
          buttonName="register"
        />
      </div>
    </div>
    <div class="categories-container">
      <Button size="btn-medium" active="active" buttonName="All"/>
      <Button size="btn-medium" buttonName="Events"/>
      <Button size="btn-medium" buttonName="Resources"/>
    </div>
    <MainContainer :data="data"/>
  </div>
</template>

<script>
import Button from "../components/Button.vue";
import MainContainer from "./MainContainer.vue";

import data from '../data.json';

export default {
  name: "AppBody",
  components: {
    Button,
    MainContainer
  },
  data() {
    return {
      data
    }
  }
};
</script>

<style lang="scss">
$regular: 400;
$normal: 500;
$semi-bold: 600;
$bold: 700;

.application-body {
  width: 100%;
  background-color: #312a2a;
  padding: 0px 40px;
  .app-header {
    margin: 40px 0px;
    display: flex;
    justify-content: space-between;
    .search-container {
      .search-form {
        input {
          width: 494px;
          padding: 20px 20px 20px 49px;
          font-family: Raleway, sans-serif;
          font-weight: $regular;
          font-size: 16px;
          color: #ffffff;
          outline: none;
          background: #362f2f;
          border: none;
          border-radius: 5px;
        }
        i {
          position: absolute;
          font-size: 25px;
          color: #ffffff;
          margin: 15px;
        }
      }
    }
    .auth-btn-group {
      margin: 0px 25px;
      display: flex;
      button {
        padding: 0px 5px;
      }
    }
  }
  .categories-container {
    margin: 28px 0px;
    display: flex;
    flex-wrap: wrap;
  }
}
</style>
