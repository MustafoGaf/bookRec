<template>
    <div style="display:flex; gap:3px; justify-content: center;
    align-items: center">
        <star-icon v-for="(_,i) in 5" :key="i" :selected="selectedStars > i" @click="handleClick(i)" />
    </div>
           <button type="button" class="btn btn-primary"  id="liveToastBtn" @click="isRated = true">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-send-fill" viewBox="0 0 16 16">
  <path d="M15.964.686a.5.5 0 0 0-.65-.65L.767 5.855H.766l-.452.18a.5.5 0 0 0-.082.887l.41.26.001.002 4.995 3.178 3.178 4.995.002.002.26.41a.5.5 0 0 0 .886-.083zm-1.833 1.89L6.637 10.07l-.215-.338a.5.5 0 0 0-.154-.154l-.338-.215 7.494-7.494 1.178-.471z"></path>
</svg>
                Оценить
              </button>

    
</template>
<script setup>
import StarIcon from './StarIcon.vue'
const emit = defineEmits(['updateSelectedStars'])
defineProps({
    selectedStars:Number
})
function handleClick(i){
    emit('updateSelectedStars', i)
}
</script>
<style scoped>
.btn{
     display: flex;
    align-items: center;
    align-content: center;
    justify-content: center;
    width: 100%;
    height: 31px;
    gap:10px;
    margin-top: 10px;
}
svg {
    cursor: pointer;
}
</style>