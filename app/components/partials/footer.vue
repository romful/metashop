<template>
  <footer>
  <div class="bg-black">
    <div class="container mx-auto py-16 flex flex-col md:flex-row justify-between">
      <div class="flex items-center justify-center py-6">
        <img src="~/static/images/opensea-realestate.png" alt="Todoist Logo" class="block object-contain h-12" />
      </div>
      <div class="flex items-center justify-center py-6">
        <img src="~/static/images/thesandbox-realestate.png" alt="Slack Logo" class="block object-contain h-12" />
      </div>
      <div class="flex items-center justify-center py-6">
        <img src="~/static/images/polygon-matic.png" alt="Typeform Logo" class="block object-contain h-12" />
      </div>
    </div>
  </div>
  <div class="container mt-12 mb-3 mx-auto grid grid-cols-2 gap-10 md:grid-cols-3 lg:grid-cols-11 lg:gap-20">
    <div class="col-span-3">
      <img src="~/static/images/uploads/logo.svg" alt="Typeform Logo" class="block object-contain h-12" />

      <p class="my-4 text-xs leading-normal text-gray-100">
        The best  digital marketplace for real estate collectibles and non-fungible tokens (NFTs). Buy, sell, and discover exclusive digital items.
      </p>
      <p>
        <img src="~/static/images/opensea.svg" alt="OpenSea" class="mx-2 inline-block object-contain" />
        <img src="~/static/images/discord.svg" alt="Discord" class="mx-2 inline-block object-contain" />
        <img src="~/static/images/twitter.svg" alt="Twitter" class="mx-2 inline-block object-contain" />
        <img src="~/static/images/instagram.svg" alt="Instagram" class="mx-2 inline-block object-contain" />
      </p>
    </div>
    <nav class="col-span-1 md:col-span-1 lg:col-span-2">
      <p class="mb-3 text-md font-semibold text-gray-200 tracking-wider">Assets</p>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">Services</a>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">Assets Collections</a>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">Partnership</a>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">Digital lands</a>
    </nav>
    <nav class="col-span-2 md:col-span-1 lg:col-span-2">
      <p class="mb-3 text-md font-semibold text-gray-200 tracking-wider">Support</p>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">Contact us</a>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">Discord channel</a>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">FAQ</a>
    </nav>
    <nav class="col-span-1 md:col-span-1 lg:col-span-2">
      <p class="mb-3 text-md font-semibold text-gray-200 tracking-wider">Resources</p>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">News</a>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">Twitter</a>
    </nav>
    <nav class="col-span-1 md:col-span-1 lg:col-span-2">
      <p class="mb-3 text-md font-semibold text-gray-200 tracking-wider">Company</p>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">About Us</a>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">Investors</a>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">Careers</a>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">Terms of Service</a>
      <a class="flex mb-3 text-sm font-normal text-gray-100 transition md:mb-2 hover:text-gray-200" href="#">Privacy Policy</a>
    </nav>
  </div>

  <div class="container mx-auto flex flex-col items-start justify-between pt-10 mt-10 border-t border-gray-100 md:flex-row md:items-center">
    <p class="mb-0 text-xs text-left text-gray-100 md:mb-0">Copyright &copy; 2021 Metashop RealEstate</p>
  </div>
  <Cookie />
</footer>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';

@Component
export default class Footer extends Vue {}
</script>

<style lang="scss">
.footer {
  background-color: $bluise;
}
</style>
