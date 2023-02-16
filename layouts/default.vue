<template>
    <div>
        <header class="shadow-md bg-white p-4 text-xl">
            <NuxtLink class="mr-3" to="/">Home</NuxtLink>
            <NuxtLink class="mr-3" to="/about">About</NuxtLink>
            <NuxtLink to="/products">Products</NuxtLink>
        </header>
        <div>
            <slot />
        </div>
    </div>
</template>

<style scoped>
    .router-link-exact-active {
        color: red;
    }
</style>
