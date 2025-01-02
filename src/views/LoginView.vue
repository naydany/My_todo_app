<template>
  <v-container>
    <v-card class="pa-4 mx-auto" width="400">
      <v-card-title class="text-center">Login here</v-card-title>
      <v-card-item>
        <v-form @submit.prevent="submit">
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
          <v-checkbox
            v-model="form.remember"
            color="success"
            label="Remember me"
            value="Data has been saved"
            hide-details
          >
          </v-checkbox>
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
      <v-card-action>
        <div class="mx-4">
          <v-btn block to="/register"> Register </v-btn>
        </div>
      </v-card-action>
    </v-card>
  </v-container>
</template>

<script setup lang="js">
import {ref} from "vue";

const form = ref({
  email: "",
  password: "",
});
const isloading = ref(false);

function submit() {
    isloading.value = true;

    setTimeout(() => {
        isloading.value=false;
        alert(JSON.stringify(form.value))
    }, 3000);
}
</script>
