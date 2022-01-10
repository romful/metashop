<template>
  <section class="assets">
    <div style="background: #010F36" class="w-full py-10">

      <div class="breadcrumbs container mx-auto">
        <div class="text-white text-xs">
          <a href="/">Home</a> / Contact Us
        </div>
      </div>

      <div class="container mx-auto">
        <h1 class="text-white text-2xl sm:text-3xl md:text-4xl font-bold">Contact Us</h1>
      </div>

    </div>

    <div class="form grid grid-cols-1 md:grid-cols-3 container rounded-lg bg-white pr-32 pl-16 py-8">
      <div class="col-span-1">
        <div class="text-lg">Contact Information</div>
        <div>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec semper lacus. Nulla facilisi. In hac habitasse platea dictumst. Us et netus et malesuada fames ac turpis egestas</p>
          <p>Proin auctor enim et mi vestibulum pretium.</p>
        </div>
        <div>
          +65347 983 387
        </div>
        <div>
          <a href="mailto:ranref@cuotuga.gov">ranref@cuotuga.gov</a>
        </div>

      </div>
      <div class="col-span-2">
        <div class="text-lg">Send Us a Message</div>
        <form method="post" class="grid  grid-cols-1 md:grid-cols-2">
          <div>
            <label class="text-sm">First Name</label>
            <input class="rounded bg-gray-500 text-black" type="text" name="firstname" />
          </div>
          <div>
            <label class="text-sm">Last Name</label>
            <input class="rounded bg-gray-500 text-black" type="text" name="lastname" />
          </div>
          <div>
            <label class="text-sm">Email</label>
            <input class="rounded bg-gray-500 text-black" type="email" name="email" />
          </div>
          <div>
            <label class="text-sm">Phone</label>
            <input class="rounded bg-gray-500 text-black" type="tel" name="phone" />
          </div>
          <div class="col-span-2">
            <label class="text-sm col-span-2">Subject</label>
            <input class="rounded bg-gray-500 text-black" type="text" name="phone" />
          </div>
          <div class="col-span-2">
            <label class="text-sm">Message</label>
            <textarea class="rounded bg-gray-500 text-black h-16" name="message"></textarea>
          </div>
          <div class="col-span-2 text-right">
            <button type="submit" class="transition duration-300 text-center w-40 p-2 leading-4 border border-white bg-transparent hover:bg-white hover:text-gray-900">Submit</button>
          </div>
        </form>
      </div>
    </div>

  <div style="background: #010F36">
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
