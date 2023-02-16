<template>
    <div class="max-w-sm rounded overflow-hidden shadow-lg text-center m-auto mt-40">
        <img class="h-64 w-64 m-auto" :src="product.image" alt="Sunset in the mountains">
        <div class="px-6 py-4">
            <div class="font-bold text-xl mb-2">{{ product.title }} ${{ product.price }}</div>
        </div>
    </div>
</template>

<script setup>
const { id } = useRoute().params
const uri = `https://fakestoreapi.com/products/${id}`
const { data: product } = await useFetch(uri)
</script>

<style scoped>

</style>