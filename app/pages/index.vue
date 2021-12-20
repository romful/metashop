<template>
  <section class="home">

    <div class="px-4 py-32 md:py-32 w-full bg-center bg-cover bg-black bg-no-repeat" style="background-image: url(/images/home.png); min-height: 425px;">
      <h1 class="metaverse-real-estat text-center text-white text-4xl sm:text-5xl md:text-6xl font-bold">Metaverse Real Estate</h1>
      <h2 class="welcome-to-the-futur text-center text-white text-2xl sm:text-2xl md:text-2xl">Welcome to the future of property assets</h2>
    </div>

    <div class="rectangle container py-12 md:py-20 px-16 md:pl-24 md:pr-64 w-full mx-auto my-20 bg-right-bottom bg-cover rounded-lg bg-no-repeat" style="background-image: url(/images/Rectangle.png)">
      <div class="title text-white text-3xl sm:text-4xl md:text-5xl leading-tight font-bold mb-10">
        Available for your game,<br />
        experience and land
      </div>
      <div class="text text-white lg:mr-64">
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec semper lacus. Nulla facilisi. In hac habitasse platea dictumst. Us et netus et malesuada fames ac turpis egestas</p>
        <p>Proin auctor enim et mi vestibulum pretium.</p>
      </div>
    </div>

    <div class="container grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 mx-auto my-20 gap-24 justify-center">
      <div class="max-w-sm mx-auto rounded overflow-hidden shadow-lg bg-white">
        <img class="w-full" src="~/static/images/asset1.svg" alt="Sunset in the mountains" />
        <div class="px-6 py-4">
          <div class="grid grid-cols-2 justify-between">
            <div>
              <div class="font-semibold text-xs text-gray-600">by <span>Creator Name</span></div>
              <div class="font-bold text-sm">Name #7380</div>
            </div>
            <div>
            	<div class="text-xs text-gray-600 text-right">Top bid</div>
            	<div class="bids font-semibold text-sm text-right"><img class="inline-block mr-1 mb-1" src="~/static/images/bids.svg" />100.00</div>
            </div>
          </div>
          <hr class="my-3" />
          <div class="text-sm font-medium text-gray-600"><img class="inline-block mr-2 mb-1" src="~/static/images/favorite.svg" />128</div>
        </div>
      </div>
      <div class="max-w-sm mx-auto rounded overflow-hidden shadow-lg bg-white">
        <img class="w-full" src="~/static/images/asset1.svg" alt="Sunset in the mountains" />
        <div class="px-6 py-4">
          <div class="grid grid-cols-2 justify-between">
            <div>
              <div class="font-semibold text-xs text-gray-600">by <span>Creator Name</span></div>
              <div class="font-bold text-sm">Name #7380</div>
            </div>
            <div>
            	<div class="text-xs text-gray-600 text-right">Top bid</div>
            	<div class="bids font-semibold text-sm text-right"><img class="inline-block mr-1 mb-1" src="~/static/images/bids.svg" />100.00</div>
            </div>
          </div>
          <hr class="my-3" />
          <div class="text-sm font-medium text-gray-600"><img class="inline-block mr-2 mb-1" src="~/static/images/favorite.svg" />128</div>
        </div>
      </div>
      <div class="max-w-sm mx-auto rounded overflow-hidden shadow-lg bg-white">
        <img class="w-full" src="~/static/images/asset1.svg" alt="Sunset in the mountains" />
        <div class="px-6 py-4">
          <div class="grid grid-cols-2 justify-between">
            <div>
              <div class="font-semibold text-xs text-gray-600">by <span>Creator Name</span></div>
              <div class="font-bold text-sm">Name #7380</div>
            </div>
            <div>
            	<div class="text-xs text-gray-600 text-right">Top bid</div>
            	<div class="bids font-semibold text-sm text-right"><img class="inline-block mr-1 mb-1" src="~/static/images/bids.svg" />100.00</div>
            </div>
          </div>
          <hr class="my-3" />
          <div class="text-sm font-medium text-gray-600"><img class="inline-block mr-2 mb-1" src="~/static/images/favorite.svg" />128</div>
        </div>
      </div>
    </div>

    <div class="discover container px-16 md:px-32 py-12 md:pt-20 md:pb-48 mx-auto my-20 w-full bg-bottom bg-cover rounded-lg bg-no-repeat" style="background-image: url(/images/Discover.png)">
      <div class="title text-white text-center text-3xl sm:text-4xl md:text-5xl leading-tight font-bold mb-10">
        Incorporate real estate assets, grow your land´s value
      </div>
      <div class="text text-white text-center">
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec semper lacus. Nulla facilisi. In hac habitasse platea dictumst. Us et netus et malesuada fames ac turpis egestas</p>
        <p>Proin auctor enim et mi vestibulum pretium.</p>
      </div>
    </div>

    <div class="rectangle container py-12 md:py-20 px-16 md:pl-24 md:pr-64 w-full mx-auto my-20 bg-right-bottom bg-cover rounded-lg bg-no-repeat" style="background-image: url(/images/Rectangle.png)">
      <div class="title text-white text-3xl sm:text-4xl md:text-5xl leading-tight font-bold mb-10">
        Owner of the assets you buy,<br />
        thanks to NFT´s blockchain.
      </div>
      <div class="text text-white lg:mr-64">
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec semper lacus. Nulla facilisi. In hac habitasse platea dictumst. Us et netus et malesuada fames ac turpis egestas</p>
        <p>Proin auctor enim et mi vestibulum pretium.</p>
      </div>
    </div>

  </section>


  

</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

@Component({
  // Called to know which transition to apply
  transition() {
    return 'slide-left';
  },
})
export default class Home extends Vue {
  welcomeText = settings.welcomeText;

  get posts(): Post[] {
    return this.$store.state.posts;
  }

  isSignedUp = false;

  form = {
    email: '',
  };

  encode(data): string {
    return Object.keys(data)
      .map((key) => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`)
      .join('&');
  }

  validEmail(email): boolean {
    // eslint-disable-next-line
    const re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    return re.test(email);
  }

  async handleSubmit(): Promise<void> {
    if (!this.validEmail(this.form.email)) {
      this.$refs.emailInput.focus();
      return;
    }

    try {
      await fetch('/', {
        method: 'POST',
        headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
        body: this.encode({ 'form-name': 'signups', ...this.form }),
      });

      this.isSignedUp = true;
    } catch (error) {
      console.error(error);
    }
  }
}
</script>
