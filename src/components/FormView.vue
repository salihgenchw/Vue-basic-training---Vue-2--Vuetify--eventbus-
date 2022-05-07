<template>
  <v-container>
    <v-row class="text-center d-flex justify-center">
      <v-col cols="10">
        <v-form ref="form" lazy-validation>
          <v-text-field
            v-model="person.name"
            :counter="10"
            label="Name"
            required
          ></v-text-field>

          <v-text-field
            v-model="person.email"
            label="Description"
            required
          ></v-text-field>

          <div class="d-flex justify-end">
            <v-btn color="warning" @click="addPerson"> Kaydet </v-btn>
          </div>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import { eventBus } from "../main";

export default {
  name: "FormView",

  data() {
    return {
      person: {
        id: null,
        name: null,
        email: null,
      },
    };
  },
  methods: {
    addPerson() {
      eventBus.$emit("addPerson", this.person);
      this.person = {
        name: null,
        email: null,
        id: null,
      };
    },
  },
};
</script>
