<template>
<div class="form-check">
  <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1"  @change="handleChange(janr)">
  <label class="form-check-label" for="flexRadioDefault1">
   {{genre}}
  </label>
</div>
</template>
<script setup>

defineProps({ 
    genre :String, 
    default: Boolean
})
const emit = defineEmits(['updateJanr'])
const handleChange = (janr) => {
  emit('updateJanr', janr)
  
}
</script>