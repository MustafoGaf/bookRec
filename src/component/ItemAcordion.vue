<template>
<div class="form-check">
  <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1"  @change="handleChange(genre)" :checked='currentGanr == genre'>
  <label class="form-check-label" for="flexRadioDefault1">
   {{genre}}
  </label>
</div>
</template>
<script setup>

defineProps({ 
    genre :String, 
    default: Boolean, 
    currentGanr:String
})
const emit = defineEmits(['updateGanr'])
const handleChange = (janr) => {
  emit('updateGanr', janr)
  
}
</script>