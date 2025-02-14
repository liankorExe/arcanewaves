<template>
    <div class="p-8 max-w-[95rem] mx-auto text-white">
        <h1 class="text-4xl md:text-5xl font-extrabold text-center uppercase tracking-widest mb-8 
                   text-transparent bg-gradient-to-r from-blue-500 via-blue-300 to-blue-500 bg-clip-text">
            SORTS
        </h1>


        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 gap-y-8">
            <div 
                v-for="(sort, index) in sorts" 
                :key="sort.nom" 
                class="flex justify-center items-center w-full cursor-pointer"
                @click="openSlideover(sort)"
            >
                <div class="holographic-card border-2 border-white/80 w-full">
                    <div class="holographic-overlay"></div>

                    <img :src="sort.image" :alt="sort.nom" class="w-full h-full object-cover rounded-md">

                    <div class="absolute bottom-4 bg-black/50 px-4 py-2 rounded-md z-10">
                        <h2 class="text-xl font-bold text-white">{{ sort.nom }}</h2>
                    </div>
                </div>
            </div>
        </div>

        <USlideover v-model="isOpen">
            <UCard class="flex flex-col flex-1" :ui="{ body: { base: 'flex-1' }, ring: '', divide: 'divide-y divide-gray-100 dark:divide-gray-800' }">
                <template #header>
                    <div class="flex items-center justify-between">
                        <h3 class="text-base font-semibold leading-6 text-gray-900 dark:text-white">
                            {{ selectedSort.nom }}
                        </h3>
                        <UButton color="gray" variant="ghost" icon="i-heroicons-x-mark-20-solid" class="-my-1" @click="isOpen = false" />
                    </div>
                </template>

                <p class=" text-lg text-gray-200">
                    {{ selectedSort.description }}
                </p>
            </UCard>
        </USlideover>
    </div>
</template>

<script setup>
import { ref } from "vue";

const sorts = ref([
    { nom: "Boule de Feu", image: "/bouledefeu2.png", description: "Projette une boule de feu explosive qui inflige des dégâts aux ennemis touchés." },
    { nom: "Soin", image: "/heal2.png", description: "Soigne immédiatement une partie de votre vie." },
    { nom: "Onde de Choc", image: "/ondedechoc2.png", description: "Crée une onde qui repousse et endommage les ennemis." },
    { nom: "Regen Mana", image: "/regenmana2.png", description: "Restaure progressivement votre mana sur une courte durée." },
    { nom: "Bientôt...", image: "/soon.png", description: "Un nouveau sort sera bientôt disponible." },
]);

const isOpen = ref(false);
const selectedSort = ref({ nom: "", description: "" });

const openSlideover = (sort) => {
    selectedSort.value = sort;
    isOpen.value = true;
};
</script>

<style>
.holographic-container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
}

.holographic-card {
    width: 100%;
    max-width: 16rem; 
    height: 28rem;
    position: relative;
    overflow: hidden;
    border-radius: 15px;
    transition: all 0.5s ease;
    background: #111;
    display: flex;
    justify-content: center;
    align-items: center;
}

/* Overlay Holographique */
.holographic-overlay {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: linear-gradient(
        0deg, 
        transparent, 
        transparent 30%, 
        rgba(255,255,255,0.3)
    );
    transform: rotate(-45deg);
    transition: all 0.5s ease;
    opacity: 0;
}

.holographic-card:hover {
    transform: scale(1.05);
    box-shadow: 0 0 20px rgba(255, 255, 255, 0.5);
}

.holographic-card:hover .holographic-overlay {
    opacity: 1;
    transform: rotate(-45deg) translateY(100%);
}
</style>
