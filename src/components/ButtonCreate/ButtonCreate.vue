<template>
  <button class="button-create" @click="handleClick" :disabled="isLoading">
    <span v-if="isLoading" class="loader"></span>
    <span v-else>Создать</span>
  </button>
</template>

<script>
export default {
  name: 'ButtonCreate',
  data() {
    return {
      isLoading: false,
    };
  },
  methods: {
    handleClick() {
      // Включите состояние загрузки после нажатия на кнопку
      this.isLoading = true;

      // Здесь можно выполнить асинхронные операции, например, запрос на сервер

      // Затем отключите состояние загрузки, когда операция завершится
      setTimeout(() => {
        this.isLoading = false;
      }, 3000); // Пример задержки на 3 секунды
    },
  },
};
</script>

<style scoped>
.button-create {
  border: 1px solid lightgray;
  border-radius: 3px;
  background-color: white;
  color: black;
  font-family: Arial, sans-serif;
  padding: 8px 16px;
  cursor: pointer;
  outline: none;
  position: relative; /* Для позиционирования прелоадера */
}

.button-create:hover {
  background-color: dodgerblue;
  color: white;
}

.loader {
  border: 2px solid rgba(0, 0, 0, 0.2);
  border-top: 2px solid dodgerblue;
  border-radius: 50%;
  width: 16px;
  height: 16px;
  animation: spin 1s linear infinite;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 1;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>
