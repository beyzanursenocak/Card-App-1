<template>
  <v-container class="grey lighten-5" >
  <v-grid> 
    <v-row class="d-flex justify-content-between">

      <v-col cols="6" md="6">
        <HelloWorld :product="products"/>
        
      </v-col>
      <v-col cols="6">
        <v-form ref="form" v-model="valid" lazy-validation>
          <h3>Edit Form</h3>
          <v-text-field
            v-model="products.image"
            :rules="imageRules"
            label="Image"
            required>
        </v-text-field>

        <v-text-field
            v-model="products.title"
            :rules="titleRules"
            label="Title"
            required>
        </v-text-field>

          <v-text-field
            v-model="products.date"
            :rules="dateRules"
            label="Date"
            required
          >
          
        </v-text-field>

        <v-text-field
            v-model="products.link"
            :rules="link"
            label="Link"
            required
          >
        </v-text-field>

          <v-btn
            style="background-color: lightgreen"
            class="mx-2"
            @click="reset"
            elevation="24"
            rounded
          >
            Reset Form
          </v-btn>
        </v-form>

      </v-col>

    </v-row>
  </v-grid>
  </v-container>
</template>

<script>
import HelloWorld from "./../components/HelloWorld.vue";
export default {
  components: {
    HelloWorld,
  },
  data: () => ({
    valid: true,
    image: "",
    imageRules: [
      (v) => !!v || "Image is required",
      (v) =>
        (v && v.length <= 1000) || "Image must be less than 1000 characters",
    ],
    titleRules: [
      (v) => !!v || "Title is required",
      (v) => /.+@.+\..+/.test(v) || "Title must be valid",
    ],
    date: "",
    dateRules: [
      (v) => !!v || "Date is required",
      (v) => /.+@.+\..+/.test(v) || "Date must be valid",
    ],
    link: "",
    linkRules: [
      (v) => !!v || "Link is required",
      (v) => /.+@.+\..+/.test(v) || "Link must be valid",
    ],
    products :
              {
                title : "product 1" ,
               image : 'https://static.euronews.com/articles/stories/06/88/46/44/320x180_cmsv2_cc722e78-e285-594f-a10d-91edd442b037-6884644.jpg',
               date : '12-05-2022' ,
               link : 'https://stackoverflow.com/questions/46955147/enter-with-keyup-event-not-working-in-vue'
              },
  }),
  methods: {
    reset() {
      this.$refs.form.reset();
    },
  },
};
</script>