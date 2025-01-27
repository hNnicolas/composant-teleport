<template>
  <button @click="open = true" class="btn btn-primary">Confirmer l'achat</button>
  <Teleport to="body">
    <div
      v-if="open"
      @click="open = false"
      class="calc d-flex flex-row justify-content-center align-items-center"
    >
      <div @click.stop class="modal-container">
        <h3>Confirmation de votre commande</h3>
        <ul>
          <li>Du contenu</li>
          <li>Du contenu</li>
          <li>Du contenu</li>
        </ul>
        <button @click.stop="open = false" class="btn btn-danger">Confirmer la commande</button>
      </div>
    </div>
  </Teleport>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const open = ref(false)
</script>

<style lang="scss">
.calc {
  position: absolute;
  top: 0;
  width: 100%;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(2px);
}

.modal-container {
  background-color: white;
  border-radius: var(--border-radius);
  border: var(--border);
  padding: 30px;
}
</style>
