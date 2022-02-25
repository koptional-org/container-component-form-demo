<template>
  <div>
    <div
      class="
        text-center
        bg-blue-500
        text-lg
        font-semibold
        tracking-wide
        text-white
        py-2
      "
    >
      <h2>Container-Component-Form Example</h2>
    </div>
    <div class="container mx-auto pt-6">
      <h2 class="font-medium text-xl text-center">Example</h2>
      <p>
        This is just a minimal example to show the
        container-component-form(-modal) architecture. Click the button below to
        bring up the modal with the form inside!
      </p>
      <div class="text-center">
        <button
          type="button"
          class="
            mt-6
            px-3
            py-1
            rounded-md
            text-white
            bg-indigo-600
            font-medium
            hover:bg-indigo-800
            cursor-pointer
          "
          @click="showModal = true"
        >
          Show me the modal!
        </button>
      </div>
    </div>
    <Modal v-if="showModal" @hide-modal="showModal = false">
      <template slot="modalBody">
        <DemoContainer @finished="showModal = false" />
      </template>
    </Modal>
  </div>
</template>

<script lang="ts">
import Modal from '@/components/MultiUse/Modal.vue'
import DemoContainer from '@/components/Demo/Container.vue'
export default {
  components: {
    Modal,
    DemoContainer,
  },
  data() {
    return {
      showModal: false,
    }
  },
}
</script>
