<template>
    <div class=" max-w-[95rem] mx-auto text-white">

        <h1 class="text-4xl md:text-5xl font-extrabold text-center uppercase tracking-widest mb-28
                   text-transparent bg-gradient-to-r from-blue-500 via-blue-300 to-blue-500 bg-clip-text">
            SHOP
        </h1>

        <div class="flex flex-col md:flex-row items-center justify-center gap-12">
            <div class="w-full md:w-1/2 flex justify-center">
                <img src="/shop.png" alt="Shop" class="w-[90%] md:w-[70%] transform -rotate-6 shadow-lg shadow-white/5 rounded-lg">
            </div>

            <div class="w-full md:w-1/2 space-y-4 bg-white/5 p-6 rounded-lg shadow-md">
                <p class="text-lg text-gray-200 leading-relaxed">
                    <span class="text-blue-300 font-semibold">Comment ça marche ?</span>
                    <ul class="list-disc list-inside text-gray-300 mt-2 space-y-1">
                        <li>Utiliser la touche <UKbd>B</UKbd> pour ouvrir la boutique.</li>
                        <li>Cliquez sur un sort pour afficher ses détails à droite.</li>
                        <li>Si vous avez assez de pièces, cliquez sur le <span class="text-green-400 font-semibold">bouton vert</span> pour l'acheter.</li>
                        <li>Les sorts achetés apparaîtront dans votre inventaire et pourront être utilisés.</li>
                    </ul>
                </p>
            </div>
        </div>
        <div class="h-20"></div>
    </div>
</template>

