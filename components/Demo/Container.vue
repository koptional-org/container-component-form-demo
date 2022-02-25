<template>
  <div>
    <DemoComponent
      :submitted="submitted"
      :loading="loading"
      @submit="handleSubmit($event)"
    />
  </div>
</template>
<script lang="ts">
import DemoComponent from './Component.vue'

interface FormModel {
  first: string
  last: string
  email: string
  state: string
}

export default {
  components: {
    DemoComponent,
  },
  data() {
    return {
      submitted: false,
      loading: false,
    }
  },
  methods: {
    handleSubmit(formModel: FormModel) {
      this.loading = true
      this.apiRequest(formModel)
      //   this.$emit('finished')
    },
    apiRequest(formModel: FormModel) {
      setTimeout(() => {
        console.log(JSON.stringify(formModel))
        this.submitted = true
        this.loading = false
      }, 2000)
    },
  },
}
</script>