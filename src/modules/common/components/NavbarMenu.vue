<template>
    <nav class="w-full bg-transparent">
        <div class="container mx-auto flex h-16 items-center justify-between px-4">
            <!-- Logo - lado izquierdo -->
            <div class="flex items-center">
                <a href="/" class="flex items-center">
                    <span class="text-xl font-bold">MiLogo</span>
                </a>
            </div>

            <!-- Opciones de navegación - visibles en desktop -->
            <div class="hidden space-x-4 md:flex">
                <a href="/opcion1" class="text-sm font-medium transition-colors hover:text-primary">
                    Mi Perfil
                </a>
                <a href="/opcion2" class="text-sm font-medium transition-colors hover:text-primary">
                    Mis Proyectos
                </a>
                <a href="/opcion3" class="text-sm font-medium transition-colors hover:text-primary">
                    Contactame
                </a>
            </div>

            <!-- Menú de hamburguesa - visible en móviles -->
            <button @click="toggleSidebar" class="md:hidden p-2 rounded-md hover:bg-gray-100" aria-label="Menú">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
                    stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                    class="h-5 w-5">
                    <line x1="4" x2="20" y1="12" y2="12"></line>
                    <line x1="4" x2="20" y1="6" y2="6"></line>
                    <line x1="4" x2="20" y1="18" y2="18"></line>
                </svg>
            </button>
        </div>

        <!-- Sidebar - se abre desde la izquierda -->
        <Transition name="slide">
            <div v-if="isOpen" class="fixed inset-0 z-50 flex">
                <!-- Overlay oscuro -->
                <div class="fixed inset-0 bg-black/20" @click="closeSidebar" aria-hidden="true"></div>

                <!-- Sidebar -->
                <div class="relative flex w-[240px] max-w-[calc(100%-3rem)] flex-col bg-white shadow-lg">
                    <div class="p-4 border-b">
                        <div class="flex items-center justify-between">
                            <span class="text-xl font-bold">MiLogo</span>
                            <button @click="closeSidebar" class="p-2 rounded-md hover:bg-gray-100"
                                aria-label="Cerrar menú">
                                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
                                    fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" class="h-5 w-5">
                                    <path d="M18 6 6 18"></path>
                                    <path d="m6 6 12 12"></path>
                                </svg>
                            </button>
                        </div>
                    </div>
                    <div class="flex-1 overflow-auto p-4">
                        <div class="flex flex-col space-y-4">
                            <a href="/opcion1" class="text-sm font-medium transition-colors hover:text-primary"
                                @click="closeSidebar">
                                Opción 1
                            </a>
                            <a href="/opcion2" class="text-sm font-medium transition-colors hover:text-primary"
                                @click="closeSidebar">
                                Opción 2
                            </a>
                            <a href="/opcion3" class="text-sm font-medium transition-colors hover:text-primary"
                                @click="closeSidebar">
                                Opción 3
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </Transition>
    </nav>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const isOpen = ref(false);

function toggleSidebar() {
    isOpen.value = !isOpen.value;

    // Prevenir scroll cuando el sidebar está abierto
    if (isOpen.value) {
        document.body.style.overflow = 'hidden';
    } else {
        document.body.style.overflow = '';
    }
}

function closeSidebar() {
    isOpen.value = false;
    document.body.style.overflow = '';
}
</script>

<style lang="css" scoped>
.slide-enter-active,
.slide-leave-active {
    transition: transform 0.3s ease;
}

.slide-enter-from,
.slide-leave-to {
    transform: translateX(-100%);
}
</style>