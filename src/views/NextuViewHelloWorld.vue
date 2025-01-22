<!--
 Composition méthode
<script lang="ts">
import { ref } from 'vue'

export default {
  name: 'NextuViewHelloWorld',
  props: {
    count: {
      type: Number,
      default: 2,
    },
  },
  setup(props) {
    const message = ref('Bonjour tout le monde')
    const countData = props.count
    return {
      message,
      countData,
    }
  },
}
</script>
-->
<script lang="ts" setup>
import { ref } from 'vue'
const message = ref('Bonjour tout le monde')
const props = defineProps<{
  count: number
}>()
const countData = props.count
</script>
<template>
  <div>{{ message }} {{ countData }}</div>
</template>
<style></style>
