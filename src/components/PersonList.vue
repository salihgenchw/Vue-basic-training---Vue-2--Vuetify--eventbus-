<template>
  <v-container v-if="this.personArr.length > 0">
    <v-divider></v-divider>
    <h2 class="text-center mt-5">PersonList</h2>
    <v-row class="text-center d-flex justify-center mt-5">
      <v-col
        v-for="person in personArr"
        :key="person.id"
        class="col-lg-4 col-md-6 col-sm-10 col-xs-10"
      >
        <v-card>
          <v-card-title class="d-flex justify-center">
            <h3 class="headline">{{ person.name }}</h3>
          </v-card-title>
          <v-card-text>
            <p>{{ person.email }}</p>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import { eventBus } from "../main";
export default {
  name: "PersonList",
  data() {
    return {
      personArr: [],
    };
  },
  created() {
    eventBus.$on("addPerson", (person) => {
      this.personArr.push(person);
    });
  },
};
</script>
