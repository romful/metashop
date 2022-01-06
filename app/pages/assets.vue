<template>
  <section class="assets">
    <div style="background: #010F36" class="w-full pt-10">

      <div class="breadcrumbs container mx-auto">
        <div class="text-white text-xs">
          <a href="/">Home</a> / Assets
        </div>
      </div>

      <div class="container mx-auto">
        <h1 class="text-white text-2xl sm:text-3xl md:text-4xl font-bold">Property Assets</h1>
      </div>

    </div>

    <div class="assets w-full">
      <div style="background: #010F36" class="w-full pt-2">
        <div class="container mx-auto grid grid-cols-1 md:grid-cols-2">
          <ul class="col-span-1 flex justify-start items-start text-white text-xs font-ligh uppercase mt-2">
            <li class="px-2 mr-8 font-semibold border-b-2 border-blue-700">
              <a href="#">Housing</a>
            </li>
            <li class="px-2 mr-8">
              <a href="#">Lands</a>
            </li>
            <li class="px-2 mr-8">
              <a href="#">Buildings</a>
            </li>
            <li class="px-2 mr-8">
              <a href="#">Accessories</a>
            </li>
          </ul>
          <div class="col-span-1 flex justify-end items-end text-white text-xs font-medium mb-2">
            <div class="px-2 mx-4">Filter</div>
            <div class="px-2 mx-4">Sort</div>
            <input class="rounded border-none text-black px-2 py-1" type="search" />
          </div>
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
