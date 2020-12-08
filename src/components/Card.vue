<template>
    <div class="card" style="width: 18rem;">
        <!-- use v-bind for the source of the image-->
        <img class="card-img-top" v-bind:src="'http://image.tmdb.org/t/p/w500'+theShow.poster_path" alt="Card image cap">
        <div class="card-body">
            <!-- Here we are binding the name and overview for theShow-->
            <h5 class="card-title">{{theShow.name}}</h5>
            <p class="card-text">{{theShow.overview}}</p>
        </div>
    </div>
</template>

<script>

export default {
    name: "Card",
    props: ['theShow']  
}
</script>
