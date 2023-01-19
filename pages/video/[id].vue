<template>
    <div>
        <h1>YT {{ $route.params.id }}</h1>
        <p>Path: {{ $route.path }}</p>
        <p>Path: {{ $route }}</p>
        
        <p>{{ continent }}</p>
        <p>{{ mountain }}</p>

        
    </div>
</template>


<script setup>
      const players = await fetch('http://localhost:3000/test.json').then((res) => res.json())
      console.log(players)

      const filteredMountain = players.find(
        (el) =>
          el.name.toLowerCase() === $route.params.id  ||  el.slug === params.mountain
      )
      if (filteredMountain) {
        return Promise.resolve({
          continent: filteredMountain.continent,
          mountain: filteredMountain.title
        })
      } 


//works
// const { data:players, pending, refresh } = await useAsyncData(
//    () => $fetch("test.json")
// )








</script>