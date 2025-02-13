<template>
    <nav :class="navClass">
        <div class="flex p-3 justify-between items-center transition-all duration-300">
            <div class="pl-4">
                <a href="#"><img src="/logo.png" alt="" :class="logoClass"></a>
            </div>
            <div class="flex space-x-5 items-center pr-8">
                <a href="#">Accueil</a>
                <a href="#description">Description</a>
                <a href="#sorts">Sorts</a>
                <a href="#touches">Touches</a>
            </div>
        </div>
    </nav>
</template>


<script setup>
import { ref, onMounted, onUnmounted, computed } from 'vue'

const hasScrolled = ref(false)

const handleScroll = () => {
    hasScrolled.value = window.scrollY > 10
}

onMounted(() => {
    window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll)
})

const navClass = computed(() =>
    hasScrolled.value
        ? "fixed top-0 left-0 w-full z-50 backdrop-blur-md bg-white/2 transition-all duration-300"
        : "fixed top-0 left-0 w-full z-50 backdrop-blur-none bg-transparent transition-all duration-300"
)

const logoClass = computed(() =>
    hasScrolled.value
        ? "h-12 transition-all duration-300" 
        : "h-20 transition-all duration-300"
)
</script>
