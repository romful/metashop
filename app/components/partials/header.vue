<template>
  <header class="container mx-auto">
<nav>
  <div class="max-w-7xl mx-auto px-2 sm:px-6 lg:px-8">
    <div class="relative flex items-center justify-between h-16">
      <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
        <button v-on:click="mobile_menu" type="button" class="mobile-menu-button inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white" aria-controls="mobile-menu" aria-expanded="false">
          <span class="sr-only">Open main menu</span>
          <svg class="block h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
          <svg class="hidden h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>
      <div class="flex-1 flex items-center justify-center sm:items-stretch sm:justify-between">
        <div class="flex-shrink-0 flex items-center">
          <nuxt-link to="/">
            <img :src="logo" alt="Logo" />
          </nuxt-link>
        </div>
        <div class="hidden sm:flex flex-col justify-center">
          <ul class="flex space-x-4">
            <li>
              <nuxt-link to="/blog" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">Services</nuxt-link>
            </li>
            <li v-for="(page, index) in pages" :key="index">
              <nuxt-link :to="`/${page.slug}`" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">{{ page.title }}</nuxt-link>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
  <div class="hidden absolute w-full" id="mobile-menu" style="background: #021651">
    <ul class="px-2 pt-2 pb-3 space-y-1">
      <li>
        <nuxt-link to="/blog" class="text-gray-300 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium">Services</nuxt-link>
      </li>
      <li v-for="(page, index) in pages" :key="index">
        <nuxt-link :to="`/${page.slug}`" class="text-gray-300 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium">{{ page.title }}</nuxt-link>
      </li>
    </ul>
  </div>
</nav>
  </header>
</template>



<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

@Component
export default class Header extends Vue {
  get pages(): Page[] {
    return this.$store.state.pages;
  }
  mobile_menu(){
    const menu = document.querySelector("#mobile-menu");
    menu.classList.toggle("hidden");
  }
  logo = settings.logo;
}
</script>

<style lang="scss">
.nav {
  ul li > a {
    &.nuxt-link-active {
      color: $bluise;
      @apply font-bold;
    }
  }
}
</style>
