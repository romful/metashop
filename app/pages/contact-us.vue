<template>
  <section class="assets">
    <div style="background: #010F36" class="w-full pt-10">

      <div class="breadcrumbs container mx-auto">
        <div class="text-white text-xs">
          <a href="/">Home</a> / Contact Us
        </div>
      </div>

      <div class="container mx-auto">
        <h1 class="text-white text-2xl sm:text-3xl md:text-4xl font-bold">Contact Us</h1>
      </div>

    </div>

    <div class="form">FORM</div>

    <div class="container grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 mx-auto my-20 gap-24 justify-center">
      <div class="max-w-sm mx-auto rounded-lg overflow-hidden shadow-lg bg-white">
        <img class="w-full" src="~/static/images/1.png" alt="Sunset in the mountains" />
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
      <div class="max-w-sm mx-auto rounded-lg overflow-hidden shadow-lg bg-white">
        <img class="w-full" src="~/static/images/2.png" alt="Sunset in the mountains" />
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
      <div class="max-w-sm mx-auto rounded-lg overflow-hidden shadow-lg bg-white">
        <img class="w-full" src="~/static/images/3.png" alt="Sunset in the mountains" />
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
