<template>
  <div id="app">
    <div class="container grid-xs py-2">
      <img
        class="img-responsive img-logo"
        src="@/assets/logo.png"
        alt="Todo Lista em Vue"
      />

      <form @submit.prevent="addTodo(todo)">
        <div class="input-group">
          <input
            type="text"
            v-model="todo.descricao"
            class="form-input"
            placeholder="Novo todo"
          />
          <button class="btn btn-primary input-group-btn">Adicionar</button>
        </div>
      </form>
      <div class="todo_list">
        <div class="tile flex-centered" v-for="t in todos" :key="t.id">
          <div class="tile-icon">
            <div>
              <i class="icon icon-time"></i>
            </div>
          </div>
          <dir class="tile-content">
            <div class="tile-subtitle">{{ t.descricao }}</div>
          </dir>
          <div class="tile-action">
            <button class="btn btn-link">Concluido</button>
            <button class="btn btn-link">
              <span class="text-error">Remover </span>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return { todos: [], todo: { checked: false } };
  },
  methods: {
    addTodo(todo) {
      todo.id = Date.now();
      this.todos.push(todo);
      this.todo = { checked: false };
    },
  },
};
</script>


<style scoped>
.img-logo {
  max-width: 200px;
  margin: 0 auto;
}

.todo_list {
  padding-top: 2rem;
}
</style>

