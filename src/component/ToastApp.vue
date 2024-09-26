<template>
    <div class="toast-container position-fixed bottom-0 end-0 p-3">
  <div id="liveToast" class="toast" role="alert" aria-live="assertive" aria-atomic="true">
    <div class="toast-body">
      {{message}}
    </div>
  </div>
</div>
</template>

<script setup>
defineProps({
    message : String
})
</script>