<template>
  <div>
    <div v-if="submitted" class="text-center p-2">
      <p class="text-green-700">Success! Your information has been saved</p>
    </div>
    <Form @submit="$emit('submit', $event)" />
    <div v-if="loading" class="flex flex-row justify-center py-2">
      <Loader />
    </div>
  </div>
</template>
<script lang="ts">
import Form from './Form.vue'
import Loader from '@/components/MultiUse/Loader.vue'
export default {
  components: {
    Form,
    Loader,
  },
  props: {
    submitted: {
      type: Boolean,
      required: true,
    },
    loading: {
      type: Boolean,
      required: true,
    },
  },
}
</script>