<template>
    <div class="flex items-center justify-center h-screen">
        <div class="max-w-sm rounded overflow-hidden shadow-lg text-center">
            <img class="h-64 w-64 m-auto" :src="product.image" alt="Sunset in the mountains">
            <div class="px-6 py-4">
                <div class="font-bold text-xl mb-2">{{ product.title }}</div>
                {{ product.description }}
                <div class="px-6 pt-4 pb-2">
                    <span
                        class="inline-block bg-green-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">${{
                            product.price
                        }}</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const { id } = useRoute().params
const uri = `https://fakestoreapi.com/products/${id}`
const { data: product } = await useFetch(uri)

if(!product.value){
    throw createError({statusCode: 404, statusMessage: 'Product not found'})
}
</script>

<style scoped>

</style>