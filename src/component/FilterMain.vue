<template>
    <div>
      <div class="accordion" id="accordionExample">
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingOne">
      <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
        Жанры
      </button>
    </h2>
    <div id="collapseOne" class="accordion-collapse collapse show" aria-labelledby="headingOne" data-bs-parent="#accordionExample">
      <div class="accordion-body">
        <item-acordion 
        v-for="janr of janrs" 
        :key="janr.id" 
        :genre='janr.genre' 
        :currentGanr='currentGanr'
        v-on:updateGanr='(ganr)=>currentGanr=ganr' />
      </div>
  <div style="display:flex; gap:10px;justify-content: center;
    margin-bottom: 10px">
    <button type="button" class="btn btn-primary" @click="$emit('filter', currentGanr)">Преминить</button>
    <button type="button" class="btn btn-danger" @click="handleReset">Сбросить</button>
  </div>
    </div>
  </div>
  
  
</div>
      

        
       
  
    </div>
</template>
<script setup>
import { ref } from 'vue'
import janrs from '../data/janr'
import ItemAcordion from './ItemAcordion.vue'
const currentGanr = ref('Фантастика')
const emit = defineEmits(['filter'])
function handleReset(){
  currentGanr.value='';
  emit('filter', '')
}
</script>