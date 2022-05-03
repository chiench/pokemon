<template>
  <div class="screen">
    <h1>one</h1>
    <card-component
      v-for="(card, index) in cardContext"
      :key="index"
    ></card-component>
  </div>
</template>

<script>
import CardComponent from "./CardComponent.vue";
export default {
  name: "MainSreen",
  props: {
    cardContext: {
      type: Array,
    },
  },
  components: {
    CardComponent,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
