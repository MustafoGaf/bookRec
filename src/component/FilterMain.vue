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
        <item-acordion v-for="janr of janrs" :key="janr.id" :genre='janr.genre' @updateJanr='(janr)=>alert(janr)' />
      </div>
  <div style="display:flex; gap:10px;justify-content: center;
    margin-bottom: 10px">
    <button type="button" class="btn btn-primary">Преминить</button>
    <button type="button" class="btn btn-danger">Сбросить</button>
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
const currentJanr = ref('')
</script>