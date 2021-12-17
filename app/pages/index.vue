<template>
  <section class="home">

    <div class="py-32 md:py-32 w-full bg-center bg-contain bg-black bg-no-repeat" style="background-image: url(/images/home.png); min-height: 425px;">
      <h1 class="metaverse-real-estat text-center text-white text-4xl sm:text-5xl md:text-6xl font-bold">Metaverse Real Estate</h1>
      <h2 class="welcome-to-the-futur text-center text-white text-2xl sm:text-2xl md:text-2xl">Welcome to the future of property assets</h2>
    </div>

    <div class="rectangle px-24 py-20 w-full mx-auto my-24 bg-right-bottom bg-cover rounded-lg bg-no-repeat" style="background-image: url(/images/Rectangle.png); max-width: 1003px">
      <div class="title text-white text-3xl sm:text-4xl md:text-5xl leading-tight font-bold mb-10">
        Available for your game,<br />
        experience and land
      </div>
      <div class="text text-white" style="padding-right: 45%;">
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec semper lacus. Nulla facilisi. In hac habitasse platea dictumst. Us et netus et malesuada fames ac turpis egestas</p>
        <p>Proin auctor enim et mi vestibulum pretium.</p>
      </div>
    </div>

   <div class="grid grid-cols-2 gap-10 justify-center lg:grid-cols-3">
         <div class="max-w-sm rounded overflow-hidden shadow-lg">
  <img class="w-full" src="~/static/images/asset1.svg" alt="Sunset in the mountains">
  <div class="px-6 py-4">
    <div class="font-bold text-xl mb-2">The Coldest Sunset</div>
    <p class="text-gray-700 text-base">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.
    </p>
  </div>
  <div class="px-6 pt-4 pb-2">
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#photography</span>
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#travel</span>
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#winter</span>
  </div>
</div>
        <div class="max-w-sm rounded overflow-hidden shadow-lg">
  <img class="w-full" src="~/static/images/asset1.svg" alt="Sunset in the mountains">
  <div class="px-6 py-4">
    <div class="font-bold text-xl mb-2">The Coldest Sunset</div>
    <p class="text-gray-700 text-base">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.
    </p>
  </div>
  <div class="px-6 pt-4 pb-2">
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#photography</span>
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#travel</span>
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#winter</span>
  </div>
</div>
        <div class="max-w-sm rounded overflow-hidden shadow-lg">
  <img class="w-full" src="~/static/images/asset1.svg" alt="Sunset in the mountains">
  <div class="px-6 py-4">
    <div class="font-bold text-xl mb-2">The Coldest Sunset</div>
    <p class="text-gray-700 text-base">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.
    </p>
  </div>
  <div class="px-6 pt-4 pb-2">
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#photography</span>
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#travel</span>
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#winter</span>
  </div>
</div>
    </div>

 

    <div class="discover px-32 pt-20 pb-48 mx-auto my-24 w-full bg-bottom bg-cover rounded-lg bg-no-repeat" style="background-image: url(/images/Discover.png); max-width: 1003px">
      <div class="title text-white text-center text-3xl sm:text-4xl md:text-5xl leading-tight font-bold mb-10">
        Incorporate real estate assets, grow your land´s value
      </div>
      <div class="text text-white text-center">
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec semper lacus. Nulla facilisi. In hac habitasse platea dictumst. Us et netus et malesuada fames ac turpis egestas</p>
        <p>Proin auctor enim et mi vestibulum pretium.</p>
      </div>
    </div>

    <div class="rectangle px-24 py-20 w-full mx-auto my-24 bg-right-bottom bg-cover rounded-lg bg-no-repeat" style="background-image: url(/images/Rectangle.png); max-width: 1003px">
      <div class="title text-white text-3xl sm:text-4xl md:text-5xl leading-tight font-bold mb-10">
        Owner of the assets you buy,<br />
        thanks to NFT´s blockchain.
      </div>
      <div class="text text-white" style="padding-right: 45%;">
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
