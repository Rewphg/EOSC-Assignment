<script setup>
</script>

<template>

  <body>
    <div class="Container">
      <v-container fill-width fluid>
        <v-row align="center" justify="center">
          <v-col style="font-size:24px;">Shopping List</v-col>
        </v-row>
      </v-container>
      <div>
        <input v-model="currentItem" placeholder="add wishing list.." @input="event => currentItem = event.target.value"
          @keyup.enter="addToList()">
        <button v-on:click="addToList()">Add to List</button>
        <button v-on:click="removeAll()">remove all</button>
      </div>
      <div class="TableLabel">
        <div v-for="(i, index) in lable" :key="index">
          {{ i }}
        </div>
      </div>
      <div class="divider"></div>
      <ul id="ShoppingListTable">
        <li v-for="(i, index) in items" :key="index">
          <div class="itemContainer">
            {{  i  }}
            <button v-on:click="removeItem(index)">remove</button>
          </div>
        </li>
      </ul>
    </div>
  </body>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
      currentItem: "",
      items: [],
      lable: ["Name", "|" ,"Action"]
    };
  },
  methods: {
    getPlaceholder() {
      return 'Add Shopping List'
    },
    addToList() {
      if (this.currentItem != "") {
        this.items.push(this.currentItem)
        this.currentItem = ""
      }
    },
    removeAll() {
      this.items = []
    },
    removeItem(id) {
      if (id == 0) {
        this.items.splice(0, 1)
      } else {
        this.items.splice(id, id)
      }
    }
  }
};
</script>

<style scoped>
body {
  margin: 0;
  padding: 0;
}

#ShoppingListTable {
  width: 100%;
  max-width: 600px;
  display: flex;
  flex-direction: column;
  gap: 12px;
  padding-top: 24px;
  list-style-type: decimal;
}

.divider {
  height: 1px;
  width: 80%;
  max-width: 580px;
  margin-top: 12px;
  background-color: white;
}

.TableLabel {
  width: 100%;
  max-width: 600px;
  margin-top: 12px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}

.Container {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.itemContainer {
  width: 100%;
  display: flex;
  justify-content: space-between;
}
</style>
