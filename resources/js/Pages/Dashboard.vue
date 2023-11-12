<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import Card from '@/Components/Card.vue';
import { Head } from '@inertiajs/vue3';


const comp_accessories = [
    {
        id: 1,
        name: 'Tama Drums',
        thumbnail: 'https://th.bing.com/th/id/R.09ad22a41210531cf6f3e060b52ca004?rik=iChCdGzAzO1OVg&riu=http%3a%2f%2fcdns3.gear4music.com%2fmedia%2f24%2f240418%2f600%2fpreview.jpg&ehk=tgMMruzj9WYf5JCZD8zE2xKhmFX9gv%2bOdRJHnnJUzr0%3d&risl=&pid=ImgRaw&r=0',
        price: '42,999.00 Php'
    },

];
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-900 leading-tight">Dashboard</h2>
        </template>

        <div class="max-w-5xl mx-auto mt-8 mb-8">
          <table class="w-full bg-white rounded-lg shadow-lg">
            <thead class="bg-gray-200 text-black">
              <tr>
                <th class="p-4">Drum Name</th>
                <th class="p-4">Photo</th>
                <th class="p-4">Price</th>
                <th class="p-4">Actions</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="comp_accessory in comp_accessories" :key="comp_accessory.id" class="hover:bg-gray-100">
                <td>
                  <div class="p-4">{{ comp_accessory.name }}</div>
                </td>
                <td>
                  <div class="p-4">
                    <img :src="comp_accessory.thumbnail" alt="" class="w-20 h-20 rounded-full">
                  </div>
                </td>
                <td>
                  <div class="p-4 text-gray-900">{{ comp_accessory.price }}</div>
                </td>
                <td>
                  <div class="p-4">
                    <button class="bg-blue-500 text-white py-2 px-4 rounded-full hover:bg-blue-700 hover:text-gray-100">
                      Buy Now
                    </button>
                  </div>
                </td>
              </tr>
            </tbody>
          </table>
        </div>



          <div v-for="comp_accessory in comp_accessories" :key="comp_accessory.id" class="rounded-lg shadow-lg max-w-3xl mx-auto">
            <div class="grid grid-cols-2 gap-4 p-4">
                <div class="bg-gray-100 rounded-lg shadow-md">
                    <img :src="comp_accessory.thumbnail" alt="" class="w-full h-64 object-cover rounded-lg">
                </div>
                <div class="bg-white rounded-lg shadow-md p-4">
                    <h2 class="text-xl font-semibold text-gray-900">{{ comp_accessory.name }}</h2>
                    <p class="text-gray-700">{{ comp_accessory.description }}</p>
                    <div class="flex items-center justify-between mt-4">
                        <span class="text-gray-600 line-through">{{ comp_accessory.retailPrice }}</span>
                        <span class="text-blue-600">{{ comp_accessory.price }}</span>
                    </div>
                    <button class="bg-blue-500 text-white py-2 px-4 rounded-full mt-4 hover:bg-blue-700 hover:text-gray-100">
                        Buy Now
                    </button>
                </div>
            </div>
        </div>

        <div class="bg-gray-200 py-8">
          <div class="max-w-screen-xl mx-auto">
            <div class="grid grid-cols-1 md:grid-cols-1 lg:grid-cols-1 gap-1">
              <div v-for="comp_accessory in comp_accessories" :key="comp_accessory.id">
                <div class="bg-white rounded-lg shadow-md">
                  <div class="overflow-hidden rounded-t-lg">
                    <img :src="comp_accessory.thumbnail" alt="Product Image" class="w-full h-60 object-cover">
                  </div>
                  <div class="p-4">
                    <h2 class="text-xl font-semibold text-gray-900">{{ comp_accessory.name }}</h2>
                    <p class="text-gray-700 mt-2">{{ comp_accessory.description }}</p>
                    <div class="flex justify-between items-center mt-4">
                      <span class="text-gray-500 line-through">{{ comp_accessory.retailPrice }}</span>
                      <span class="text-blue-600 text-xl">{{ comp_accessory.price }}</span>
                    </div>
                    <div class="mt-4">
                      <button class="bg-blue-500 text-white py-2 px-4 rounded-full hover:bg-blue-700 hover:text-gray-100">
                        Buy Now
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>



    </AuthenticatedLayout>
</template>

<style scoped>
.grid1{
    display: grid;
    grid-template-columns: repeat(3,1fr);
    gap: 24px 24px;
}


</style>
