<template>
  <div>
    <!-- <h1>Continent: {{ continent }}</h1>
    <h2>Mountain: {{ mountain }}</h2> -->
    <p>Path: {{ $route.path }}</p>

    <ul v-if="players">
          <li v-for="player of players">
              <NuxtLink :to="'/video/' + player.name">{{ player.name }}</NuxtLink>
          </li>
      </ul>


    <!-- <p>{{ mountains }}</p> -->
    <!-- <p>{{ test }}</p> -->
    <NuxtLink to="/">Back to Mountains</NuxtLink>



  </div>
</template>


<script setup>
      const players = await fetch('http://localhost:3000/test.json').then((res) => res.json())
      console.log(players)

      // const filteredMountain = players.find(
      //   (el) =>
      //     el.name.toLowerCase() === params.continent &&
      //     el.slug === params.mountain
      // )
      // if (filteredMountain) {
      //   return {
      //     continent: filteredMountain.continent,
      //     mountain: filteredMountain.title
      //   }
      // } 



//works
// const { data:players, pending, refresh } = await useAsyncData(
//    () => $fetch("test.json")
// )






</script>

