<template>
  <label :for="inputInfo.inputName" class="flex flex-col"
    >{{ inputInfo.label }}
    <input
      class="shadow-sm border-gray-300 rounded-lg m-2"
      type="text"
      :name="inputInfo.inputName"
      :value="value"
      @input="$emit('input', $event.target.value)"
    />
  </label>
</template>
<script>
export default {
  props: ["inputInfo", "value"],
};
</script>
