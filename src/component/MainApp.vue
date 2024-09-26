<template>
    <section class="row container-fluid" style="margin-top: 20px">
        <div class="col-md-3">
            <filter-main v-on:filter='(ganr)=>genre=ganr' />
        </div>
  <div class="col-md-9">
    <div class="input-group mb-3">
  <span class="input-group-text" id="basic-addon1"><img src="/search.svg" alt=""></span>
  <input type="text" class="form-control" placeholder="Book name, author or ISBM" aria-label="book" aria-describedby="basic-addon1" v-model="search">
</div>

<div>
    <h3>Books</h3>
</div>
<div class="row row-cols-4">
  <books-app v-for="book in filerBooks" :key="book.id" :book='book'  />

</div>
  </div>

    </section>
</template>
<script setup >
import { computed, ref } from 'vue'
import FilterMain from './FilterMain.vue'
import BooksApp from './BooksApp.vue'
import books from '../data/books'
const search = ref('')
const genre = ref('')
const setGenre = (val) => {
genre.value = val
}

const filerBooks = computed(() => {
  return books.filter((book) => book.name.toLowerCase().includes(search.value.toLowerCase())).filter(book => book.genre.includes(genre.value)

   )
})
</script>