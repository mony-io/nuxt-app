<template>
    <div>
        <h3 class="font-semibold text-2xl my-6">All Producs</h3>
        <div class="grid grid-cols-6 gap-3">
            <div class="col-span-3 md:col-span-2 lg:col-span-2 xl:col-span-1" v-for="p in products">
                <ProductCard :product="p" />
            </div>
        </div>
    </div>
</template>
  
<script setup>
//  fetch the products
const { data: products } = await useFetch('https://fakestoreapi.com/products')

useHead({
    title: "Nuxt Dojo | Merch",
    meta: [
        { name: 'description', content: "Nuxt 3 Merch" }
    ]
})

definePageMeta({
    layout: "products",
})
</script>