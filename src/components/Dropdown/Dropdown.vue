<template>
  <div class="dropdown">
    <input
        v-model="selectedItem"
        @click="toggleDropdown"
        placeholder="Выберите элемент"
    />
    <ul v-if="isOpen" class="dropdown-list">
      <li v-for="item in items" :key="item" @click="selectItem(item)">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Dropdown',
  data() {
    return {
      isOpen: false,
      selectedItem: '',
      items: ['Элемент 1', 'Элемент 2', 'Элемент 3', 'Элемент 4'], // Замените на свои элементы
    };
  },
  methods: {
    toggleDropdown() {
      this.isOpen = !this.isOpen;
    },
    selectItem(item) {
      this.selectedItem = item;
      this.isOpen = false;
    },
  },
};
</script>

<style scoped>
.dropdown {
  position: relative;
  display: inline-block;
}

input {
  padding: 8px;
}

.dropdown-list {
  position: absolute;
  top: 100%;
  left: 0;
  border: 1px solid lightgray;
  background-color: white;
  list-style: none;
  padding: 0;
  margin: 0;
  max-height: 150px;
  overflow-y: auto;
}

li {
  padding: 8px;
  cursor: pointer;
}

li:hover {
  background-color: #f0f0f0;
}
</style>
