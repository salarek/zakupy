<template>
  <div class="item" v-bind:class="{ completed: item.completed }">
    <link
      href="https://fonts.googleapis.com/css2?family=Dancing+Script&family=Gloria+Hallelujah&display=swap"
      rel="stylesheet"
    />
    <h2>
      {{ item.title }}
      <button class="item" v-if="!item.completed" @click="removeItem">Kupione</button>
    </h2>
  </div>
</template>

<script>
export default {
  props: ["item"],
  methods: {
    removeItem() {
      this.$emit("removeClicked", this.item.id);
    }
  }
};
</script>

<style scoped>
.item {
  color: black;
  font-family: "Gloria Hallelujah", cursive;
}
.completed {
  opacity: 0.5;
}
.completed h2 {
  text-decoration: line-through;
  color: black;
}
.item button {
  font-size: 20px;
  color: white;
  background-color: red;
  border-radius: 50%;
}
</style>
