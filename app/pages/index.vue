<template>
  <section class="home">

    <div class="py-24 md:py-36 w-full bg-center bg-cover" style="background-image: url(/images/home.png)">
      <h1 class="metaverse-real-estat text-center text-white text-4xl sm:text-5xl md:text-6xl font-bold">Metaverse Real Estate</h1>
      <h2 class="welcome-to-the-futur text-center text-white text-2xl sm:text-2xl md:text-2xl">Welcome to the future of property assets</h2>
    </div>

    <div class="rectangle p-12 w-full bg-right-bottom bg-cover" style="background-image: url(/images/Rectangle.png)">
      <div class="title text-white text-3xl sm:text-4xl md:text-5xl font-bold">
        Available for your game,<br />
        experience and land
      </div>
      <div class="text text-white">
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec semper lacus. Nulla facilisi. In hac habitasse platea dictumst. Us et netus et malesuada fames ac turpis egestas</p>
        <p>Proin auctor enim et mi vestibulum pretium.</p>
      </div>
    </div>

    <div class="discover p-12 w-full bg-bottom bg-cover" style="background-image: url(/images/Discover.png)">
      <div class="title text-white text-center text-3xl sm:text-4xl md:text-5xl font-bold">
        Discover our assets
      </div>
      <div class="text text-white text-center">
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
