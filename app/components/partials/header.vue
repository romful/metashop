<template>
<header class="z-30 w-full px-2 py-4 bg-transparent sm:px-4">
  <div class="container flex items-center justify-between mx-auto">
    <img src="~/static/images/uploads/logo.svg" alt="Typeform Logo" class="block object-contain h-12" />


    <div class="flex items-center space-x-5 rtl:space-x-reverse">
     <ul class="relative hidden space-x-10 md:inline-flex rtl:space-x-reverse">
        <li><a href="#" class="text-gray-800 hover:text-gray-900 font-bold">Home</a></li>
        <li><a href="#" class="text-gray-800 hover:text-gray-900">About</a></li>
        <li><a href="#" class="text-gray-800 hover:text-gray-900">Blog</a></li>
        <li><a href="#" class="text-gray-800 hover:text-gray-900">Pricing</a></li>
      </ul>
      <a href="#" class="rounded-sm bg-black text-white px-5 py-2 border-solid border border-black">Contact Us</a>
      <div class="inline-flex md:hidden">
        <button class="flex-none px-2 btn btn-white btn-sm" @click="open = true">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
            aria-hidden="true"
            class="w-5 h-5"
          >
            <line x1="3" y1="12" x2="21" y2="12"></line>
            <line x1="3" y1="6" x2="21" y2="6"></line>
            <line x1="3" y1="18" x2="21" y2="18"></line>
          </svg>
          <span class="sr-only">Open Menu</span>
        </button>
      
      </div>
    </div>
  </div>
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
