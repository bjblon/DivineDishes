<template>
  <div>
    <!-- {{ random.meals[0].strMealThumb }} -->
    <!-- <section>
      <h1>Welcome to Home Page</h1>
      <div v-for="(r,index) in random.meals" :key="index">
        <img :src="r.strMealThumb" alt="">
      </div>
    </section> -->
    <section>

<!-- Jumbotron -->
<div v-for="(r,index) in random.meals" :key="index"
  class="relative overflow-hidden  bg-cover bg-no-repeat p-12 text-center"
  :style="{ 'background-image': 'url(' + r.strMealThumb + ')' , 'height':'100vh' }">
  <div
    class="absolute bottom-0 left-0 right-0 top-0 h-full w-full overflow-hidden bg-fixed"
    style="background-color: rgba(0, 0, 0, 0.6)">
    <div class="flex h-full items-center justify-center">
      <div class="m-20 text-white">
        <h2 class="mb-4 text-4xl font-bold">{{ r.strMeal}}</h2>
        <h4 class="mb-6 text-sm font-semibold">{{ r.strInstructions }}</h4>
        <button
          type="button"
          class="rounded border-2 border-neutral-50 px-7 pb-[8px] pt-[10px] text-sm font-medium uppercase leading-normal text-neutral-50 transition duration-150 ease-in-out hover:border-neutral-100 hover:bg-neutral-500 hover:bg-opacity-10 hover:text-neutral-100 focus:border-neutral-100 focus:text-neutral-100 focus:outline-none focus:ring-0 active:border-neutral-200 active:text-neutral-200 dark:hover:bg-neutral-100 dark:hover:bg-opacity-10"
          data-te-ripple-init
          data-te-ripple-color="light">
          Read More 
        </button>
      </div>
    </div>
  </div>
</div>
<!-- Jumbotron -->

    </section>



  </div>
</template>

<script setup>
  const { data:random } = await useFetch("https://www.themealdb.com/api/json/v1/1/random.php");
  
</script>

<style lang="scss" scoped>
</style>