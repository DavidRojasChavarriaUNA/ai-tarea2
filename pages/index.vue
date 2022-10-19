<!-- pages/index.vue -->
<template>
  <div class="container">
   <HeaderView />
   <h3 style="margin-top: 15px">Planet Dataset</h3>
     <p>This Dataset consists different parameters for the 8 Planets of our Solar System</p>
     <p>More details please clic <NuxtLink to="https://www.kaggle.com/datasets/iamsouravbanerjee/planet-dataset" target="_blank">Here</NuxtLink></p>
   <ul>
     <li v-for="planet in planets" :key="planet.num">
       <NuxtLink :to="`/planets/${planet.num}`">{{planet.planet}}</NuxtLink>
     </li>
   </ul>
   <FooterView />
 </div>
</template>
<script setup>
  const data = await queryContent('planets').only('planetsList').findOne()
  const planets = data.planetsList
</script>