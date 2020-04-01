<template>
  <div class="event-detail">
    <div class="detail-header">
      <div class="header-title">
        {{data.title}}
        <button class="btn btn-medium primary uppercase height-fit"><i class="fa fa-share-alt"></i> share</button>
      </div>
      <div class="header-detail">
        {{data.slug}}
      </div>
      <div class="header-buttons">
        <button class="btn btn-medium">Follow</button>
      </div>
    </div>
    <div class="detail-body">
      <p>Ithaca Generator provides public access to 21st century tools and technologies like 3D printers, laser cutters, and microcontrollers. We make these tools available through affordable membership and through educational partnerships. By making these technologies accessible, we aim to transform the public’s conception of themselves from passive consumers to active designers, inventors, and innovators.</p>
    </div>
  </div>
</template>

<script>

export default {
  name: "EventDetail",
  props: {
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

.event-detail {
  min-height: 768px;
  background-color: #201919;
  width: 48%;
  .detail-header {
    background-size: cover;
    background-image: url(../assets/detail-header.png);
    padding: 64px 30px;
    .header-title {
      font-family: Raleway, sans-serif;
      font-size: 34px;
      color: #ffffff;
      font-weight: $bold;
      display: flex;
      justify-content: space-between;
      button{
        i {
          font-size: 20px;
          padding-right: 10px;
        }
      }
    }
    .header-detail {
      font-family: Raleway, sans-serif;
      font-size: 20px;
      color: #ffffff;
      font-weight: $regular;
    }
    .header-buttons {
      margin-top: 20px;
    }
  }
  .detail-body {
    p {
      color: #ffffff;
      font-family: Raleway, sans-serif;
      font-size: 16px;
      line-height: 24px;
      font-weight: $regular;
      margin: 0 30px;
    }
  }
}
</style>
