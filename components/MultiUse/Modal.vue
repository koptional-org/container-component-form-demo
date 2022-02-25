<template>
  <div class="absolute inset-0 bg-dark">
    <div class="max-w-md bg-white rounded-lg mx-auto p-4 opacity-100 mt-20">
      <div class="flex flex-row justify-end">
        <button class="p-2 mr-2 text-3xl" @click="$emit('hide-modal')">
          &times;
        </button>
      </div>
      <h3 class="text-center text-xl font-bold tracking-wide">
        Welcome to the modal!
      </h3>
      <div>
        <slot name="modalBody" />
      </div>
    </div>
  </div>
</template>
<script lang="ts">
export default {}
</script>