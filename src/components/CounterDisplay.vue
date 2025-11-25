<template>
  <div class="counter-display">
    <h3>Contador (Componente hijo)</h3>
    <p>Valor: <strong>{{ count }}</strong></p>

    <div>
      <button @click="$emit('decrement')">-</button>
      <button @click="$emit('increment')">+</button>
      <button @click="$emit('reset')">Reset</button>
    </div>

    <div class="slot">
      <slot>
        <small>Contenido por defecto del slot</small>
      </slot>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'CounterDisplay',
  props: {
    count: { type: Number, required: true }
  },
  emits: ['increment', 'decrement', 'reset']
})
</script>

<style scoped>
.counter-display { border: 1px solid #ccc; padding: 8px; border-radius: 6px; max-width: 360px; }
button { margin: 0 6px; }
.slot { margin-top: 8px; color: #555; }
</style>
