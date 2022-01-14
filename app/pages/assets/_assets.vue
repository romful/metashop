<template>
  <article class="assets" :class="assets.slug">
    <div class="py-8 md:py-16 text-center mx-auto">
      <h1 class="text-lg md:text-xl lg:text-4xl xl:text-6xl">
        {{ assets.title }}
      </h1>
    </div>

    <div v-html="$md.render(assets.content)" class="assets__content markdown pt-4 md:pt-6 md:pb-24" />
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
      const contract_token = params.assets.split("-");
      const contract = contract_token[0];
      const token = contract_token[1];
      const url = "https://api.opensea.io/api/v1/asset/" + contract + "/" + token + "/";
      const assets = {
        slug: "SLUG",
        title: params.assets,
        seoDescription: "SEO DESCRIPTION",
        seoMetaImage: null,
        content: url
      };

      return {
        assets
      };
    } catch (e) {
      throw new Error('Assets Not found');
    }
  }
}
</script>
