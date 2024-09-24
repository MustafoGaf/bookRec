<template>
    <div class="col mt-2">
            <div class="card" style="width: 12rem; position: relative;">
                <img :src='book.img' class="card-img-top" :alt="book.name">
                <div>

    <h6 @click="allText=!allText" class="card-text namebook">{{book.name}}</h6>
                </div>
                <div class="card-body">
    <p class="card-text "><strong>Aвтор: <br> </strong>{{book.author}}</p>
    <p class="card-text"><strong>ISBN: <br> </strong>{{book.ISBN}}</p>
    <p class="card-text"><strong>Жанр: <br> </strong>{{book.genre}}</p>
    <p class="card-text" style="font-size:18px"><strong>Рейтинг: </strong>{{book.rating}}</p>

                </div>
            </div>
    </div>
</template>
<script setup>
import {ref} from 'vue'
const allText = ref(false)
defineProps({
    book:Object
})

</script>

<style scoped>
.card{
    overflow: hidden;
}
.card-body{
    color: white;
    position: absolute;
    background: rgba(0, 0, 0, 0.501);
    bottom: -500px;
    height:100%;
    transition: 0.5s ease-in;
    width: 100%;
    
}
.card:hover .card-body{
    bottom: 0;
}
.card:hover img{
    filter: blur(2px);
}
.namebook {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
.allText {
    white-space: normal !important;
}
.namebook{
    padding: 10px 10px;
}
</style>