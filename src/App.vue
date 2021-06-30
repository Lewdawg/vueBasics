<template>
  <div>
    <h1>{{ title }}</h1>
    <h3>{{ subTitle }}</h3>
    <!-- <input type="text" ref="apple" />
    <button @click="handleClick">Click Me</button> -->

    <div v-if="showModel">
      <Modal theme="sale" @close="showM">
        <template v-slot:links>
          <a href="#">Sign Up</a>
          <a href="#">Login</a>
        </template>
      </Modal>
    </div>

    <div v-if="showModel2">
      <Modal @close="showM2">
        <h2>This is the second Modal</h2>
      </Modal>
    </div>

    <button @click="showM">Show Model</button>
    <button @click="showM2">Show Model Two</button>
  </div>
</template>

<script>
import Modal from "./components/Model.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "My First Vue Tutorial",
      subTitle: "With Net Ninja!",
      showModel: false,
      showModel2: false,
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.apple);
      this.$refs.apple.classList.add("active");
      this.$refs.apple.focus();
    },
    showM() {
      this.showModel = !this.showModel;
    },
    showM2() {
      this.showModel2 = !this.showModel2;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.button {
  padding: 15px;
}

.active {
  background-color: red;
}
</style>
