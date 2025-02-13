<template>
    <div class="p-8 max-w-[95rem] mx-auto text-white">
        <h1 class="text-4xl md:text-5xl font-extrabold text-center uppercase tracking-widest mb-8 
                   text-transparent bg-gradient-to-r from-blue-500 via-blue-300 to-blue-500 bg-clip-text">
            TOUCHES
        </h1>

        <UTable :rows="controls" :columns="columns" class="rounded-lg border border-white/20 shadow-lg bg-white/5">
            <template #touches-data="{ row }">
                <div class="flex space-x-1">
                    <UKbd v-for="key in row.touches" :key="key">{{ key }}</UKbd>
                </div>
            </template>
        </UTable>
    </div>
</template>

<script setup>
import { ref } from "vue";
import { UKbd } from "#components";

const controls = ref([
    { touches: ["Z", "↑"], action: "Avancer" },
    { touches: ["S", "↓"], action: "Reculer" },
    { touches: ["Q", "←"], action: "Aller à gauche" },
    { touches: ["D", "→"], action: "Aller à droite" },
    { touches: ["I"], action: "Ouvrir l'inventaire" },
    { touches: ["F"], action: "Démarrer un niveau" },
    { touches: ["1", "&"], action: "Sélectionner le sort 1" },
    { touches: ["2", "é"], action: "Sélectionner le sort 2" },
    { touches: ["3", '"'], action: "Sélectionner le sort 3" },
    { touches: ["4", "'"], action: "Sélectionner le sort 4" },
    { touches: ["5", "("], action: "Sélectionner le sort 5" },
    { touches: ["E"], action: "Utiliser le sort sélectionné" },
    { touches: ["B"], action: "Ouvrir la boutique" }
]);

const columns = [
    { key: "touches", label: "Touches", sortable: false },
    { key: "action", label: "Action", sortable: false }
];
</script>

<style>
.UTable {
    text-align: center;
}
</style>
