<script setup lang="ts">
import { ref } from 'vue';

const showNavBar = ref<boolean>(true);

</script>
<template>
    <div class="p-3 bg-gray-100">
        <Transition>
            <div v-if="showNavBar" class="flex justify-between items-center">
                <div class="uppercase font-bold">
                    <p class="text-2xl">Mary Store</p>
                </div>
                <div class="flex gap-4">
                    <img class="w-8 cursor-pointer" src="/search.svg" alt="Menu" @click="showNavBar = !showNavBar">
                    <img class="w-8" src="/cart.svg" alt="Menu">
                    <img class="w-8" src="/user.svg" alt="Menu">
                    <img class="w-8" src="/menu.svg" alt="Menu">
                </div>
            </div>

            <div v-else class="flex items-center">
                <img src="/back.svg" class="w-8 cursor-pointer" @click="showNavBar = !showNavBar">
                <form class="w-full">
                    <div>
                        <input type="search" id="default-search"
                            class="block p-2 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border border-gray-300 focus:ring-blue-500 focus:border-blue-500 "
                            placeholder="Search Mockups, Logos..." required>
                    </div>
                </form>
            </div>
        </Transition>
    </div>
</template>
<style>
.v-enter-active,
.v-leave-active {
    transition: opacity 0.3s ease-in-out;
}

.v-enter-from,
.v-leave-to {
    opacity: 0;
}
</style>