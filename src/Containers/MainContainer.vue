<template>
  <div class="main-container">
    <EventList :data="data"/>
    <EventDetail :data="data.collections[0]"/>
  </div>
</template>

<script>
import EventList from "./EventList.vue"
import EventDetail from "./EventDetail.vue"

export default {
  name: "MainContainer",
  components: {
    EventList,
    EventDetail
  },
  props: {
    data: {
      type: Object,
      required: true,
    }
  }
};
</script>

<style lang="scss">
.main-container {
  display: flex;
  justify-content: space-between;
}
</style>
