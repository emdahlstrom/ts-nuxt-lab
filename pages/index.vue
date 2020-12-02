<template lang="pug">
.container.mx-auto.p-20
  .flex
    left
      label name
        input.block.m-10.p-2(type='text' v-model='name')
      label age
        input.block.m-10.p-2(type='text' v-model='age')
    right
      pre.text-xs {{ $v }}

</template>

<script lang="ts">
import Vue from 'vue'
import { required, between } from 'vuelidate/lib/validators'

export default Vue.extend({
  data() {
    return {
      name: '',
      age: '',
    }
  },
  validations() {
    return {
      name: {
        required,
      },
      age: {
        required,
        between: between(0, 300),
      },
    }
  },
})
</script>

<style></style>
