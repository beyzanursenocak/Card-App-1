<template>
  <v-grid>
    <v-row>
      <v-col >
        <v-card class="mx-auto mt-5" max-width="344">
          <v-img height="200px" :src="product.image" id="images"></v-img>

          <v-card-title>
            {{ product.title }}
          </v-card-title>

          <v-card-date>
            {{ product.date }}
          </v-card-date>
          <br/>
          <br/>
              <v-card-link align-content-end="ml-left">
                {{ product.link }}
              </v-card-link>
        </v-card>
      </v-col>
    </v-row>
  </v-grid>
  </template>

<script>
export default {
  props :{
    product :{
      type: Object,
      required: true
    }
  },
  data () {
    return {
      show: false,
      
    };
  },
};
</script>