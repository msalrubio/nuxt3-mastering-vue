<template>
  <label
    class="px-4 py-2 text-white rounded-md"
    :class="modelValue ? 'bg-green-600' : 'bg-gray-500'"
  >
    <input
      type="checkbox"
      :value="modelValue"
      class="hidden"
      @input="() => $emit('update:modelValue', !modelValue)"
    />
    {{ modelValue ? 'Completed' : 'Mark as complete ' }}
  </label>
</template>
<script lang="ts" setup>
  defineProps({
    modelValue: {
      type: Boolean,
      default: false,
    },
  })

  defineEmits(['update:modelValue'])
</script>

<style scoped>
  ::selection {
    display: none;
  }
</style>
