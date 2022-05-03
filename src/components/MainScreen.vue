<template>
  <div class="screen">
    <h1>one</h1>
    <card-component
      :ref="card"
      v-for="(card, index) in cardContext"
      :key="index"
      :imageId="card"
      @checkrule="play($event)"
    ></card-component>
  </div>
  <pre>{{ card }}</pre>
</template>

<script>
import CardComponent from "./CardComponent.vue";
export default {
  name: "MainSreen",
  data() {
    return {
      ArrayTestPlay: [],
    };
  },
  props: {
    cardContext: {
      type: Array,
    },
  },
  components: {
    CardComponent,
  },
  methods: {
    play(config) {
      if (this.ArrayTestPlay.length === 2) {
        return false;
      }
      this.ArrayTestPlay.push(config);

      if (
        this.ArrayTestPlay.length === 2 &&
        this.ArrayTestPlay[0] === this.ArrayTestPlay[1]
      ) {
        console.log("Right");
      } else if (
        this.ArrayTestPlay.length === 2 &&
        this.ArrayTestPlay[0] !== this.ArrayTestPlay[1]
      ) {
        console.log(this.$refs.card.closeCard());
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
