<template>
  <div>
    <v-row justify="center" align="center">
      <v-col cols="10">
        <v-card class="mt-5 pa-5">
            <v-card-title>複数選択可能</v-card-title>
            <span>{{selected}}</span>
            <v-layout wrap>
              <v-flex v-for="genre in genres" :key="genre.id" >
                <v-checkbox v-model="selected" :label="genre.name" :value="genre.id"></v-checkbox>
              </v-flex>
            </v-layout>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selected: [],
      genres: [
        { id: 0, name: 'hitose' },
        { id: 1, name: 'jr' },
      ],
    }
  },
};
</script>