<template>
    <div class="mb-10">
        <!-- {{ ch }} -->
        <section class="loading" v-if="pending">
          <img src="~/assets/images/loading.gif" width="250" alt="">
        </section>
    <div class="container mx-auto" v-else>
      <section class="rounded-lg bg-white p-10 shadow-lg">
        <div class="mb-4 flex items-center">
          <input type="text" v-model="searchTerm" maxlength="1" class="w-full rounded-lg border border-gray-400 p-2" placeholder="Search By Letter ..." />
          <button @click="getUrl(searchTerm)" class="ml-2 rounded-lg bg-green-500 p-2 text-white hover:bg-green-600">Search</button>
        </div>
        <!-- <div class="flex">
          <label class="mr-4">
            <input type="checkbox" class="mr-2" />
            MP3
          </label>
          <label class="mr-4">
            <input type="checkbox" class="mr-2" />
            MP4
          </label>
          <label>
            <input type="checkbox" class="mr-2" />
            FLAC
          </label>
        </div> -->
      </section>

      <!-- <input type="text" v-model="ch" class="border" maxlength="1">
        <button @click="getUrl(ch)">Search</button> -->
        <section class="ml-16 mt-10">
      <div class="grid grid-cols-4">
        <div v-for="(p, index) in letters.meals" :key="index">
          <NuxtLink :to="`/products/${p.idMeal}`">
            <ProductCard :product="p" />
          </NuxtLink>
        </div>
      </div>
    </section>
    </div>
        
        
    </div>
</template>

<script setup>
    const searchTerm =ref("");
    const url = ref("https://www.themealdb.com/api/json/v1/1/search.php?f=a");
    const { data : letters , pending } = await useFetch(url, { refetch : true});
    function getUrl(searchTerm) {
        url.value = `https://www.themealdb.com/api/json/v1/1/search.php?f=${searchTerm}`
    }
</script>

<style >

</style>