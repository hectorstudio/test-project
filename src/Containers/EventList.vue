<template>
  <div class="event-list">
    <div class="event-list-header">
      <div class="header-detail">
        <div class="header-title">
          <p class="bold">{{data.title}}</p>
          <p class="regular">{{data.description}}</p>
        </div>
        <div class="header-buttons">
          <Button size="btn-medium" buttonName="Follow" />
          <Button size="btn-medium" buttonName="View details" />
        </div>
      </div>
      <div class="header-image"></div>
    </div>
    <related-resources></related-resources>
    <div class="event-list-body">
      <div class="event-list-title">
        Upcoming Events
      </div>
      <EventItem v-for="(item, index) in data.possibilities" :key="index" :data="item"/>
    </div>
  </div>
</template>

<script>
import Button from "../components/Button.vue";
import RelatedResources from "./RelatedResources.vue";
import EventItem from "../components/EventItem.vue";

export default {
  name: "EventList",
  components: {
    Button,
    RelatedResources,
    EventItem
  },
  props:{
    data: {
      type: Object,
      required: true
    }
  }
};
</script>

<style lang="scss">
$regular: 400;
$normal: 500;
$semi-bold: 600;
$bold: 700;

.event-list {
  background-color: #362f2f;
  min-height: 768px;
  width: 48%;
  display: flex;
  flex-direction: column;
  
  .event-list-header {
    background-color: #201919;
    display: flex;
    .header-detail {
      width: 60%;
      padding: 30px 0px 27px 30px;
      .header-title {
        font-family: Raleway, sans-serif;
        color: #ffffff;
        .bold {
          font-weight: $bold;
          font-size: 16px;
          margin: 0px;
        }
        .regular {
          margin: 5px 0 10px;
          color: #605f5f;
          font-weight: $regular;
          font-size: 14px;
        }
      }
      .header-buttons {
        display: flex;
        button {
          margin-right: 10px;
        }
      }
    }
    .header-image {
      width: 40%;
      overflow: hidden;
      background: linear-gradient(
        270deg,
        rgba(32, 25, 25, 0.0001) 0%,
        #201919 100%
      );
      background-image: url(../assets/item_png.png);
      img {
        height: 100%;
      }
    }
  }
  .event-list-body {
    .event-list-title {
      padding: 10px;
      font-family: Raleway, sans-serif;
      color: #ffffff;
      font-weight: $bold;
      font-size: 18px;
    }
  }
}
</style>
