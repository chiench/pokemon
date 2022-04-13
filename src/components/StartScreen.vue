<template>
  <div class="container">
    <h1>POKE MEMORIES</h1>
    <p>Select mode to start game</p>
    <div class="option">
      <ul>
        <li v-for="(option, i) in options" :key="i">
          <a :href="`${option.to}`">{{ option.name }}</a>
          <br />
          <span>{{ option.level }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      options: [
        { name: "4x4", to: "#", level: "Esay" },
        { name: "6x6", to: "#", level: "Nomarl" },
        { name: "8x8", to: "#", level: "Hard" },
        { name: "10x10", to: "#", level: "Super Hard" },
      ],
    };
  },
  methods: {},
};
</script>
<style scoped>
.container {
  text-align: center;
  padding: 20px auto;
  border: 2px solid salmon;
}
.option ul {
  display: flex;
  justify-content: center;
  list-style: none;
}
.option ul li {
  width: 100px;
  height: 100px;
  margin: auto 10px;
  padding-top: 32px;
  border: 1px solid saddlebrown;
  border-radius: 12px;
  transform: 0.4s;
}
.option ul li:hover {
  background-color: azure;
}
.option ul li a {
  text-decoration: none;
  font-family: monospace;
  font-weight: bold;
}
.option ul li span {
  font-family: monospace;
  font-weight: bold;
}
</style>
>
