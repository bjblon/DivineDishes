<template>
  <div class="mb-10">
    <section class="loading" v-if="pending">
      <img src="~/assets/images/loading.gif" width="250" alt="" />
    </section>
    <section v-else>
      <div class="p-2">
        <label for="underline_select" class="sr-only">Underline select</label>
        <select
          v-model="name"
          @change="getUrl(name)"
          id="underline_select"
          class="block py-2.5 px-0 w-full text-sm text-gray-500 text-center bg-transparent border-0 border-b-2 border-gray-200 appearance-none dark:text-gray-400 dark:border-gray-700 focus:outline-none focus:ring-0 focus:border-gray-200 peer"
        >
          <option selected>Choose Category</option>
          <option
            :value="category.strCategory"
            v-for="(category, index) in categoryData.categories"
            :key="index"
          >
            {{ category.strCategory }}
          </option>
        </select>
      </div>

      <!-- {{ meals }} -->
      <section class="ml-16 mt-10">
        <div class="grid grid-cols-4">
          <div v-for="(p, index) in meals.meals" :key="index">
            <NuxtLink :to="`/products/${p.idMeal}`">
              <ProductCard :product="p" />
            </NuxtLink>
          </div>
        </div>
      </section>
    </section>
  </div>
</template>

<script setup>
let name = "hello world";
const url = ref(`https://www.themealdb.com/api/json/v1/1/filter.php?c=Seafood`);

// Get all Categories //
const { data: categoryData } = await useFetch(
  "https://www.themealdb.com/api/json/v1/1/categories.php"
);
// Get all Categories  End //

const { data: meals, pending } = useFetch(url, { refetch: true });

function getUrl(category) {
  url.value = `https://www.themealdb.com/api/json/v1/1/filter.php?c=${category}`;
}
</script>

<style >
.loading {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>