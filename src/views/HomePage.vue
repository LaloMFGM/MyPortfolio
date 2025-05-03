<script setup lang="ts">
import NavbarMenu from '@/modules/common/components/NavbarMenu.vue';


</script>



<template>

  <div class="app-container bg-[#1a1a1a] text-white">

    <header class="relative">
      <div class="bg-dark w-full min-h-screen">
        <div class="absolute top-0 left-0 right-0 z-10">
          <navbar-menu></navbar-menu>
        </div>
        <div class="grid grid-cols-7 flex-col items-center justify-center w-full h-screen gap-4 p-4">
          <div class="flex items-center justify-center col-span-4">
            <img src="../assets/images/lalo.webp" alt="profile" class="h-[60vh] w-[60vh] 
                        object-cover 
                        mask-radial-at-center 
                        mask-radial-from-20% 
                        mask-radial-to-70%
                        animate-pulse-fade-in" />
          </div>
          <div class="flex flex-col items-start justify-center p-16 col-span-3">
            <p class="
                      text-xl 
                    text-white
                      animate-pulse-fade-in
                      w-full
                      text-[4vh]
                      mb-4
                      font-bold">
              Eduardo Mahonri Fabian Guerrero

            </p>

            <p class="text-lg 
                    text-white
                      animate-pulse-fade-in
                      w-full
                      mb-16">
              Software Developer | Web, Móvil y Backend

            </p>
            <p class="text-lg 
                    text-white
                      animate-pulse-fade-in
                      w-full">
              3 años como desarrollador de software, con experiencia integral en desarrollo móvil, web y backend,
              especialmente en la creación de sistemas SaaS. Apasionado por el aprendizaje y los desafíos que impulsan
              mi crecimiento profesional.
            </p>
          </div>

        </div>
      </div>

    </header>



    <footer>

    </footer>
  </div>


</template>



<style scoped>
.app-container {
  min-height: 100vh;
  width: 100%;
}
</style>