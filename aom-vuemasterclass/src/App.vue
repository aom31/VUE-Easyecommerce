<template>
  <div>
    <div>
      <div>Fistname</div>
      <input type="text" name="firstname" v-model="formData.firstname" />
    </div>
    <div>
      <div>Lastname</div>
      <input type="text" name="lastname" v-model="formData.lastname" />
    </div>
    <div>
      <div>Description</div>
      <textarea
        name="description"
        cols="30"
        rows="10"
        v-model="formData.description"
      ></textarea>
    </div>
    <div>
      Gender
      <div v-for="gender in genderList">
        <input
          type="radio"
          name="gender"
          :value="gender"
          v-model="formData.gender"
        />
        {{ gender }}
      </div>
    </div>

    <div>
      Interest
      <div v-for="interest in interestList">
        <input
          type="checkbox"
          name="interest"
          :value="interest"
          v-model="formData.interest"
        />
        {{ interest }}
      </div>
    </div>

    <div>
      <button @click="sendForm()">Send</button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { reactive } from "vue";
import { FormDataInput } from "./models/form";

const genderList = ["men", "women", "none"];
const interestList = ["book", "sports", "movie", "travel"];

const formData = reactive<FormDataInput>({
  firstname: "",
  lastname: "",
  description: "",
  gender: "",
  interest: [],
});

function sendForm() {
  console.log(formData);
}
</script>

<style>
/* Your styles here */
</style>
