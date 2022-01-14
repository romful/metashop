<template>
  <article class="assets" :class="assets.slug">
    <div class="py-8 md:py-16 text-center mx-auto">
      <h1 class="text-white text-lg md:text-xl lg:text-4xl xl:text-6xl">
        {{ assets.name }}
      </h1>
    </div>
    <img :src="{{ assets.image_preview_url }}" />
    <div v-html="$md.render(assets.description)" class="text-white assets__content markdown pt-4 md:pt-6 md:pb-24" />
  </article>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import { MetaInfo } from 'vue-meta';

@Component({
  head(): MetaInfo {
    return {
      title: this.assets.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.assets.seoDescription,
        },
        {
          hid: 'og:image',
          name: 'og:image',
          content: this.assets.seoMetaImage,
        },
      ],
    };
  },
})
export default class AssetsTemplate extends Vue {
  assets!: Assets;

  async asyncData({ params, payload }): Promise<{ assets: Assets }> {
    if (payload) {
      return { assets: payload };
    }

    try {
      const slug = params.assets.split("-");
      const contract = slug[0];
      const token = slug[1];
      const url = "https://api.opensea.io/api/v1/asset/" + contract + "/" + token + "/";
      const response = await fetch(url);
      let assets = await response.json();
      assets.slug = slug;
      assets.title = assets.name;
      assets.seoDescription = assets.description;
      assets.seoMetaImage = assets.image_preview_url;
      console.log(assets);

      return {
        assets
      };
    } catch (e) {
      throw new Error('Assets Not found');
    }
  }
}
</script>
