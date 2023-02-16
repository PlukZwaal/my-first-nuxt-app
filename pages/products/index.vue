<template>
    <div class="grid grid-cols-4 gap-5 m-10">
        <div v-for="product in products" :key="product">
            <div class="max-w-sm rounded overflow-hidden shadow-lg text-center">
                <img class="h-64 w-64 m-auto" :src="product.image" alt="Sunset in the mountains">
                <div class="px-6 py-4">
                    <div class="font-bold text-xl mb-2">{{ product.title }}</div>
                    <button class="bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded">
                        <NuxtLink :to="`/products/${product.id}`">View details</NuxtLink>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    const {data: products } = await useFetch('https://fakestoreapi.com/products')
</script>

<style scoped>

</style>