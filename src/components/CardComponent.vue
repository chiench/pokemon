<template>
  <div class="card">
    <pre>{{ imageId }}</pre>
    <div class="card-inner" @click="onFillip" :class="{ isFlliped: isFlliped }">
      <div class="card-face card-face-front">
        <div class="card-content-front"></div>
      </div>

      <div class="card-face card-face-back">
        <div
          :style="{
            backgroundImage: `url(${require('@/assets/images/' +
              imageId +
              '.png')})`,
          }"
          class="card-content-back"
        ></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    imageId: {
      type: [Number, String, Array, Object],
      required: true,
    },
  },
  data() {
    return {
      isFlliped: false,
    };
  },
  methods: {
    onFillip() {
      console.log(1);
      this.isFlliped = !this.isFlliped;
    },
  },
};
</script>

<style lang="css" scoped>
.card {
  display: inline-block;
  margin: 1rem 1rem;
  width: 90px;
  height: 120px;
}

.card-inner {
  width: 100%;
  height: 100%;
  position: relative;
  transition: transform 1s;
  cursor: pointer;
  transform-style: preserve-3d;
  border-radius: 10px;
}
.isFlliped {
  transform: rotateY(-180deg);
}
.card-face {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  overflow: hidden;
  border-radius: 1rem;
  padding: 1rem;
  box-shadow: 0 3px 18px 3px rgba(0, 0, 0, 0.2);
}
.card-face-back {
  background-color: var(--light);
  transform: rotateY(-180deg);
}
.card-face-front {
  background-color: var(--dark);
}
.card-content-front {
  background-image: url("../assets/images/icon_back.png");
  background-size: contain;
  background-position: center center;
  width: 100%;
  height: 100%;
  background-repeat: no-repeat;
}
.card-content-back {
  background-size: contain;
  background-position: center center;
  width: 100%;
  height: 100%;
  background-repeat: no-repeat;
}
</style>
