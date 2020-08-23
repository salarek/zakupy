<template>
  <div class="bg">
    <div class="item">
      <link
        href="https://fonts.googleapis.com/css2?family=Dancing+Script&family=Gloria+Hallelujah&display=swap"
        rel="stylesheet"
      />
      <h2>LISTA ZAKUPOW</h2>
      <input class="item" type="text" placeholder="Wpisz produkt" v-model="newItem" />

      <button class="item" @click="addItem">Dodaj</button>
    </div>
    <TodoItem v-for="item in items" :key="item.id" :item="item" @removeClicked="removeItem" />
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
  components: {
    TodoItem
  },
  data() {
    return {
      newItem: "",
      items: [
        //{ title: "zrobic zakupy", completed: false, id: 1 },
      ]
    };
  },
  methods: {
    addItem() {
      this.items.push({
        title: this.newItem,
        completed: false,
        id: Math.random()
      });
      this.newItem = "";
    },
    removeItem(id) {
      const index = this.items.findIndex(el => el.id === id);
      this.items[index].completed = true;
    }
  }
};
</script>

<style scoped>
.item {
  font-family: "Gloria Hallelujah", cursive;
  font-size: 15px;
}
.item button {
  background-color: greenyellow;
}
</style>
