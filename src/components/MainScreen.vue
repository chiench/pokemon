<template>
  <div class="screen">
    <h1>one</h1>
    <card-component
      v-for="(card, index) in cardContext"
      :key="index"
      :imageId="card"
      :card="{ index, value: card }"
      @checkrule="play($event)"
      ref="Card"
    ></card-component>
  </div>
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
      console.log(config.index);
      console.log(this.$refs.Card[config.index].onBackFilipCard());
      if (this.ArrayTestPlay.length === 2) {
        return false;
      }
      this.ArrayTestPlay.push(config);

      if (
        this.ArrayTestPlay.length === 2 &&
        this.ArrayTestPlay[0].value === this.ArrayTestPlay[1].value
      ) {
        console.log("Right");
      } else if (
        this.ArrayTestPlay.length === 2 &&
        this.ArrayTestPlay[0].value !== this.ArrayTestPlay[1].value
      ) {
        console.log("wrong");
        setTimeout(() => {
          this.$refs.Card[config.index].onBackFilipCard();
          this.$refs.Card[config.index].onBackFilipCard();
        }, 800);

        //this.$refs[`card-${this.ArrayTestPlay[0].index}`].closeCard();
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
