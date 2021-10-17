<script setup>
import { ref, provide, reactive } from 'vue'
import { menuStateKey, menuStateFactory } from '@/providers/menuState';

const state = menuStateFactory();
provide(menuStateKey, state);

</script>

<template>
  <div>
    <header class="bg-white shadow" v-if="$route.meta.title">
      <div class="px-4 py-6 mx-auto max-w-7xl sm:px-6 lg:px-8">
        <h1
          @click="state.filters.showMobileMenu = !state.filters.showMobileMenu"
          class="text-3xl font-bold leading-tight text-gray-900"
        >
          state.filters.showMobileMenu / {{ state.filters.showMobileMenu }}
        </h1>
      </div>
    </header>
    <main>
      <router-view />
    </main>
  </div>
</template>
