<template>
  <div>
    <!-- {{ meal.meals[0].strMealThumb }} -->
    <section class="loading" v-if="pending">
      <img src="~/assets/images/loading.gif" width="250" alt="">
    </section>

    <!-- component -->
    <section class="flex mt-5 mb-5 justify-center" v-else>
      <div
        class="rounded overflow-hidden border w-full lg:w-10/12 md:w-6/12 bg-white mx-3 md:mx-0 lg:mx-0"
      >
        <div class="grid grid-cols-3 sm:grid-cols-1 lg:grid-cols-3">
          <div>
            <div class="w-full flex justify-between p-3">
              <div class="flex sm:mx-auto lg:ml-5">
                <div
                  class="rounded-full h-8 w-8 bg-gray-500 flex items-center justify-center overflow-hidden"
                >
                  <img :src="meal.meals[0].strMealThumb" alt="profilepic" />
                </div>
                <span class="pt-1 ml-2 font-bold text-sm"
                  >{{ meal.meals[0].strMeal }}r</span
                >
              </div>
              <!-- <span class="px-2 hover:bg-gray-300 cursor-pointer rounded"
                ><i class="fas fa-ellipsis-h pt-2 text-lg"></i
              ></span> -->
            </div>
            <img
              class="rounded-lg w-96 h-96 bg-cover sm:mx-auto"
              :src="meal.meals[0].strMealThumb"
            />
            <!-- <div class="pt-2">
        <i class="far fa-heart cursor-pointer"></i>
        <span class="text-sm text-gray-400 font-medium">12 likes</span>
      </div> -->
          </div>
          <div class="px-3 pt-3">
            <div class="pt-10">
              <div class="mb-2 text-sm">
                <div class="long-text">
                  {{ meal.meals[0].strInstructions }}
                </div>
              </div>
              <div>
                <span class="pt-1 ml-2 font-bold text-sm"
                  >Category: {{ meal.meals[0].strCategory }}
                </span>
              </div>
              <div>
                <span class="pt-1 ml-2 font-bold text-sm"
                  >Dish: {{ meal.meals[0].strArea }}
                </span>
              </div>
              <div>
                <span class="pt-1 ml-2 font-bold text-sm">Watch On Youtube:</span>

                <div class="bg-white shadow-md rounded-lg pl-10">
                  
                  <a :href="meal.meals[0].strYoutube" target="_blank"><i class="fa-brands fa-youtube text-3xl text-red-500"></i></a>
                </div>
                
              </div>
            </div>
            <!-- <div class="text-sm mb-2 text-gray-400 cursor-pointer font-medium">View all 14 comments</div> -->
            <!-- <div class="mb-2">
        <div class="mb-2 text-sm">
          <span class="font-medium mr-2">razzle_dazzle</span> Dude! How cool! I went to New Zealand last summer and had a blast taking the tour! So much to see! Make sure you bring a good camera when you go!
        </div>
      </div> -->
          </div>

          <div>
            <span class="pt-12 flex justify-center font-bold text-sm"
              >Ingredient:</span
            >

            <div class="text-sm pt-5 px-6 flex justify-center">
              <!-- ingredient in 2 columns -->
              <div class="grid grid-cols-2 gap-4">
                <div>
                  <p>
                    {{ meal.meals[0].strIngredient1 }} :
                    {{ meal.meals[0].strMeasure1 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient2 }} :
                    {{ meal.meals[0].strMeasure2 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient3 }} :
                    {{ meal.meals[0].strMeasure3 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient4 }} :
                    {{ meal.meals[0].strMeasure4 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient5 }} :
                    {{ meal.meals[0].strMeasure5 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient6 }} :
                    {{ meal.meals[0].strMeasure6 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient7 }} :
                    {{ meal.meals[0].strMeasure7 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient8 }} :
                    {{ meal.meals[0].strMeasure8 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient9 }} :
                    {{ meal.meals[0].strMeasure9 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient10 }} :
                    {{ meal.meals[0].strMeasure10 }}
                  </p>
                </div>
                <div>
                  <p>
                    {{ meal.meals[0].strIngredient11 }} :
                    {{ meal.meals[0].strMeasure11 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient12 }} :
                    {{ meal.meals[0].strMeasure12 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient13 }} :
                    {{ meal.meals[0].strMeasure13 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient14 }} :
                    {{ meal.meals[0].strMeasure14 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient15 }} :
                    {{ meal.meals[0].strMeasure15 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient16 }} :
                    {{ meal.meals[0].strMeasure16 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient17 }} :
                    {{ meal.meals[0].strMeasure17 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient18 }} :
                    {{ meal.meals[0].strMeasure18 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient19 }} :
                    {{ meal.meals[0].strMeasure19 }}
                  </p>
                  <p>
                    {{ meal.meals[0].strIngredient20 }} :
                    {{ meal.meals[0].strMeasure20 }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
  <!-- const url = ref("https://www.themealdb.com/api/json/v1/1/search.php?f=a");
    const { data : letters , pending } = await useFetch(url, { refetch : true}); -->
</template>

<script setup>
const route = useRoute();
// const { data: meal } = await useFetch(
//   `https://www.themealdb.com/api/json/v1/1/lookup.php?i=${route.params.id}`
// );
  const url = ref (`https://www.themealdb.com/api/json/v1/1/lookup.php?i=${route.params.id}`);
  const { data : meal , pending } = await useFetch (url, { refetch  : true});

</script>

<style scoped>
.long-text {
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 14; /* Specify the desired number of lines */
  overflow: hidden;
}
.loading {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>