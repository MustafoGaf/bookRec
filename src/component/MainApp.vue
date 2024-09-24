<template>
    <section class="row container-fluid" style="margin-top: 20px">
        <div class="col-md-3">
            <filter-main/>
        </div>
  <div class="col-md-9">
    <div class="input-group mb-3">
  <span class="input-group-text" id="basic-addon1"><img src="/search.svg" alt=""></span>
  <input type="text" class="form-control" placeholder="Book name, author or ISBM" aria-label="book" aria-describedby="basic-addon1">
</div>

<div>
    <h3>Books</h3>
</div>
<div class="row row-cols-4">
  <books-app v-for="book in books" :key="book.id" :book='book'  />

</div>
  </div>

    </section>
</template>
<script setup >
import FilterMain from './FilterMain.vue'
import BooksApp from './BooksApp.vue'
import books from '../data/books'
</script>
