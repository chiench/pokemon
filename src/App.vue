<template>
  <div>
    <h1>one</h1>
    <StartScreen
      v-if="statusSwitch === 'default'"
      @show="ShowMainScreen($event)"
    ></StartScreen>
    <MainScreen
      :cardContext="this.setting.contextBlock"
      v-if="statusSwitch === 'Main'"
    ></MainScreen>

    <!-- <EndScreen></EndScreen>
    <CopyrightScreen></CopyrightScreen> -->
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import StartScreen from "./components/StartScreen.vue";
import MainScreen from "./components/MainScreen.vue";

// import EndScreen from "./components/EndScreen.vue";
// import CopyrightScreen from "./components/CopyrightScreen.vue";
import { shuffed } from "./ulits/sort";
export default {
  name: "App",
  components: {
    StartScreen,
    MainScreen,
    // EndScreen,
    // CopyrightScreen,
  },
  data() {
    return {
      setting: {
        totalOfBlock: 0,
        contextBlock: [],
        startAt: 0,
      },
      statusSwitch: "default",
    };
  },
  methods: {
    ShowMainScreen(config) {
      this.setting.totalOfBlock = config.amount;
      const firstArray = Array.from(
        { length: this.setting.totalOfBlock / 2 },
        (_, i) => i + 1
      );

      const secondArray = [...firstArray];

      this.setting.contextBlock = [...firstArray, ...secondArray];
      this.setting.contextBlock = shuffed(shuffed(this.setting.contextBlock));
      this.setting.startAt = new Date().getTime();

      //xư lý load số thẻ và ảnh vào trước khi bắt đầu

      //
      this.statusSwitch = "Main";
    },
  },
};
</script>

<style></style>
