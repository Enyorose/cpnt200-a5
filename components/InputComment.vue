<template>
  <label :for="inputInfo.inputName" class="flex flex-col"
    >{{ inputInfo.label }}
    <textarea
      class="shadow-md border-black rounded-lg m-2"
      :name="inputInfo.inputName"
      :value="value"
      @input="$emit('input', $event.target.value)"
    ></textarea>
  </label>
</template>
<script>
export default {
  props: ["inputInfo", "value"],
};
</script>
