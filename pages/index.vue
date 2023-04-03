<template>
    <div>
        <div class="flex space-x-3 text-gray-800 justify-center text-lg font-semibold  w-full m-auto my-6 bg-[#ddd] p-3">
            <a href="#">Clothes</a>
            <a href="#">Sneakers</a>
            <a href="#">Man</a>
            <a href="#">Women</a>
            <a href="#">Kids</a>
            <a href="#">Jackets</a>
            <a href="#">Hoodies</a>
            <a href="#">Sweater</a>
        </div>
        <div>
            <ImageSlider/>
        </div>
        <p class="my-6 text-2xl font-semibold">
            Trending Products
        </p>
        <div class="grid grid-cols-6 gap-3">
            <div class="col-span-3 md:col-span-2 lg:col-span-2 xl:col-span-1" v-for="p in products">
                <ProductCard :product="p" />
            </div>
        </div>
        <p class="my-6 text-2xl font-semibold">
            Popular Products
        </p>
        <div class="grid grid-cols-6 gap-3">
            <div class="col-span-3 md:col-span-2 lg:col-span-2 xl:col-span-1" v-for="p in products">
                <ProductCard :product="p" />
            </div>
        </div>
    </div>
</template>

<script setup>
const { data: products } = await useFetch('https://fakestoreapi.com/products')
</script>

<style scoped>
h2 {
    margin-bottom: 20px;
    font-size: 36px;
}

p {
    margin: 20px 0;
}
</style>