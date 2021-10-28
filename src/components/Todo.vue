<template>
  <div class="tile flex-centered">
    <div class="tile-icon">
      <div>
        <i class="icon icon-time"></i>
      </div>
    </div>
    <dir class="tile-content">
      <div class="tile-subtitle">{{ todo.description }}</div>
    </dir>
    <div class="tile-action">
      <button @click="$emit('toggle', todo)" class="btn btn-link">
        Concluido
      </button>
      <button class="btn btn-link">
        <span class="text-error">Remover </span>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    todo: { type: Object, required: true },
  },
};
</script>

<style scoped>
.checked {
  text-decoration: line-through;
  color: lightgray;
}
</style>