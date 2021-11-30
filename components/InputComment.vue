<template>
  <label :for="inputInfo.inputName">{{inputInfo.label}}
    <input class=" border-0" type="text" :name="inputInfo.inputName" :value="value" @input="$emit('input', $event.target.value)">
  </label>
</template>
<script>
export default {
  props: ['inputInfo', 'value']
}
</script>
