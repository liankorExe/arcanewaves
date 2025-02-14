<template>
  <div class="relative w-full h-screen">
    <img class="w-full h-full object-cover opacity-20" src="/background.png" alt="">

    <div class="absolute inset-0 flex flex-col items-center justify-center">
      <h1 class="font-milker text-8xl md:text-9xl font-extrabold text-white drop-shadow-lg leading-tight">
        ARCANE
      </h1>

      <h2
        class="font-milker text-6xl md:text-7xl font-extrabold text-transparent bg-gradient-to-r from-blue-400 via-white to-blue-400 bg-clip-text animate-waves drop-shadow-lg leading-tight -mt-3">
        WAVES
      </h2>

      <div class="flex space-x-4 mt-6">
        <a href="/arcanewaves.rar" download
          class="group relative px-14 py-3 bg-white text-black font-semibold rounded-full shadow-lg overflow-hidden transition-all duration-300 hover:bg-gray-200">
          <span
            class="absolute inset-0 flex items-center justify-center transition-transform duration-300 group-hover:-translate-y-full">
            Jouer
          </span>
          <span
            class="absolute inset-0 flex items-center justify-center transition-transform duration-300 translate-y-full group-hover:translate-y-0">
            🚀
          </span>
        </a>

        <a href="#description"
          class="group relative overflow-hidden px-8 py-3 border-2 border-white text-white font-semibold rounded-full flex items-center space-x-3 transition-all duration-300 hover:bg-blue-200 hover:border-blue-200 hover:text-black">
          <span class="relative z-10 tracking-widest uppercase">En savoir plus</span>
          <svg class="w-5 h-5 relative z-10 transition-transform duration-300 group-hover:translate-x-2"
            xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
          </svg>
        </a>
      </div>
    </div>

    <div class="absolute bottom-6 left-[49%] transform -translate-x-1/2 animate-bounce">
      <svg class="w-10 h-10 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
        stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
      </svg>
    </div>

    <div class="space-y-20">
      <section id="description" class="scroll-mt-10">
        <Description />
      </section>
      <section id="sorts" class="scroll-mt-10">
        <Sorts />
      </section>
      <section id="touches" class="scroll-mt-10">
        <Touches />
      </section>
      <section id="shop" class="scroll-mt-10">
        <Shop />
      </section>
      
      <Footer/>

    </div>
  </div>
</template>


<style>
html {
  scroll-behavior: smooth;
}

@keyframes waveEffect {

  0%,
  100% {
    background-position: 0% 50%;
  }

  50% {
    background-position: 100% 50%;
  }
}

.animate-waves {
  background-size: 200% 200%;
  animation: waveEffect 3s ease-in-out infinite;
}
</style>
