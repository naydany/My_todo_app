<template>
  <div class="ml-6 mt-6" @click="back">
      <v-icon>mdi-arrow-left</v-icon>
  </div>
  <v-container>
    <v-card class="pa-4 mx-auto" width="400">
      <v-card-title class="text-center"> Register </v-card-title>
      <v-card-item>
        <v-form @submit.prevent="submit">
          <v-text-field
            v-model="form.name"
            label="Name"
            variant="underlined"
            type="text"
            append-inner-icon="mdi-text"
          >
          </v-text-field>
          <v-text-field
            v-model="form.email"
            label="Email address"
            type="email"
            variant="underlined"
            append-inner-icon="mdi-email"
          >
          </v-text-field>
          <v-text-field
            v-model="form.password"
            label="Password"
            type="password"
            hint="Inter your password to acccess this website"
            variant="underlined"
            append-inner-icon="mdi-key"
          >
          </v-text-field>
          <v-btn class="mt-2" color="blue-darken-3" type="submit" block>
            <v-progress-circular
              v-if="isloading"
              color="withe"
              indeterminate
            ></v-progress-circular>
            <span v-else>Submit</span>
          </v-btn>
        </v-form>
      </v-card-item>
    </v-card>
  </v-container>
</template>

<script setup lang="js">
import {ref} from "vue";

const form = ref({
  name: "",
  email: "",
  password: "",
});

export default {
  methods:
}
const isloading = ref(false);

function submit() {
    isloading.value = true;

    setTimeout(() => {
        isloading.value=false;
        alert(JSON.stringify(form.value))
    }, 3000);
}

</script>
