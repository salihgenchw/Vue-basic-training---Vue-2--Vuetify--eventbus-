<template>
  <v-app>
    <v-app-bar app color="orange lighten-1">
      <div class="d-flex align-center">
        <h1 class="shrink mt-1 hidden-sm-and-down">AtPerson</h1>
      </div>
    </v-app-bar>

    <v-main>
      <FormView />
      <PersonList />
    </v-main>
  </v-app>
</template>

<script>
import FormView from "./components/FormView";
import PersonList from "./components/PersonList";

export default {
  name: "App",

  components: {
    FormView,
    PersonList,
  },
  created() {
    document.title = "Saturday Training";
  },
};
</script>
