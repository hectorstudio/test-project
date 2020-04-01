<template>
  <div class="event-item">
    <div class="item-status">
      <p class="large">{{ this.startDay }}</p>
      <p class="small">{{ this.monthArray[this.startMon-1] }}</p>
      <p class="large"><i class="fa fa-star"></i></p>
    </div>
    <div class="item-detail">
      <div class="item-title">
        {{ data.title }}
      </div>
      <div class="item-schedule">
        {{ this.schedule_time }}
      </div>
      <div class="item-address">
        {{ data.description }}
      </div>
    </div>
    <div class="item-image">
      <a :href="data.url" target="_blank"><img :src="this.image_url" alt="item-image" /></a>
    </div>
  </div>
</template>

<script>
export default {
  name: "EventItem",
  props: {
    data: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      startMon: "",
      startDay: 0,
      monthArray: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
      image_url: "",
      schedule_time: "",
    };
  },
  mounted() {
    let date = this.data.url_attachments[0].created_at;
    let tempArray = date.split('T');
    this.schedule_time = tempArray[0];
    tempArray = tempArray[0].split('-');
    this.startDay = parseInt(tempArray[2]);
    this.startMon = parseInt(tempArray[1]);
    this.image_url = this.data.url_attachments[0].image_url;
  }
};
</script>

<style lang="scss">
$regular: 400;
$normal: 500;
$semi-bold: 600;
$bold: 700;

.event-item {
  padding: 20px;
  border-bottom: 1px solid #201919;
  display: flex;
  div {
    display: flex;
  }
  .item-status {
    flex: 1;
    flex-direction: column;
    p {
      text-align: center;
      margin: 0px;
      color: #605f5f;
      font-family: Raleway, sans-serif;
      font-weight: $regular;
      &.small {
        font-size: 17px;
        margin-bottom: 5px;
      }
      &.large {
        font-size: 40px;
      }
    }
  }
  .item-detail {
    flex: 8;
    flex-direction: column;
    font-family: Raleway, sans-serif;
    color: #ffffff;
    margin: 0px 0px 0px 20px;
    .item-title {
      font-weight: $bold;
      font-size: 16px;
      margin: 0px;
    }
    .item-schedule {
      margin: 5px 0 0px;
      color: #605f5f;
      font-weight: $regular;
      font-size: 14px;
    }
    .item-address {
      margin: 5px 0 5px;
      color: #605f5f;
      font-weight: $regular;
      font-size: 14px;
    }
  }
  .item-image {
    justify-content: center;
    flex: 3;
    a {
      height: 100%;
      img {
        width: 100%;
      }      
    }
  }
}
</style>
