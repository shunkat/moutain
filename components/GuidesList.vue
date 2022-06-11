<template>
    <v-main class="grey lighten-2">
      <v-container>
        <v-row>
          <template>
            <v-col
              v-for="content in sections.contents" :key=content.id
              class="mt-2"
              cols="12"
            >
              <strong>{{ section.title }}</strong>
            </v-col>

            <v-col
              v-for="guide in guides.contents"
              :key="guide.id"
            >
                <nuxt-link :to="`/guides/${guide.id}/`">
                    <v-card elevation="2" height="200">
                        <v-card-title>{{ guide.name }}</v-card-title>
                        <v-img :src="guide.image.url" height="240" />
                    </v-card>
                </nuxt-link>
            </v-col>
          </template>
        </v-row>
      </v-container>
    </v-main>
</template>

<script>
export default {
    async asyncData({ $microcms }) {
        const guides = await $microcms.get({
            endpoint: "guides",
        });
        const sections = await $microcms.get({
            endpoint: "sections",
        });
        return {
            guides,
            sections,
        };  
    },
};
</script>