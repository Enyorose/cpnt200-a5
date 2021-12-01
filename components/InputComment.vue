<template>
  <label :for="inputInfo.inputName" class="flex flex-col"
    >{{ inputInfo.label }}
    <input
      class="border-2 mt-3"
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
