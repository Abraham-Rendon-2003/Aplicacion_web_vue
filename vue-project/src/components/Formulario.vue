<template>
  <b-container>
    <div>
      <b-form @submit.prevent="checkForm" action="https://vuejs.org/" method="post" novalidate>
        <b-alert variant="danger" dismissible :show="errors.length > 0">
          <b>{{ errors.length > 1 ? "Please correct the following errors:" : "Please correct the following error:" }}</b>
          <ul>
            <li v-for="error in errors" :key="error">{{ error }}</li>
          </ul>
        </b-alert>

        <b-form-group id="name-group" label="Name" label-for="name" :state="name ? null : false">
          <b-form-input id="name" v-model="name" type="text" name="name" required></b-form-input>
        </b-form-group>

        <b-form-group id="address-group" label="Address" label-for="address" :state="address ? null : false">
          <b-form-input id="address" v-model="address" type="text" name="address" required></b-form-input>
        </b-form-group>

        <b-form-group id="dob-group" label="Date of Birth" label-for="dob" :state="validDOB(dob) ? null : false">
          <b-form-input id="dob" v-model="dob" type="date" name="dob" required></b-form-input>
        </b-form-group>

        <b-form-group id="email-group" label="Email" label-for="email" :state="validEmail(email) ? null : false">
          <b-form-input id="email" v-model="email" type="email" name="email" required></b-form-input>
        </b-form-group>

        <b-form-group id="phone-group" label="Phone Number" label-for="phone" :state="validPhoneNumber(phone) ? null : false">
          <b-form-input id="phone" v-model="phone" type="tel" name="phone" required></b-form-input>
        </b-form-group>

        <b-form-group id="photo-group" label="Photo (PNG)" label-for="photo" :state="validPhotoSize(photo) ? null : false">
          <b-form-file id="photo" v-model="photo" accept=".png" required></b-form-file>
        </b-form-group>

        <b-button type="submit" variant="primary">Submit</b-button>
      </b-form>
    </div>
  </b-container>
</template>

<script>
import Vue from "vue";

export default Vue.extend({
  data() {
    return {
      errors: [],
      name: null,
      address: null,
      dob: null,
      email: null,
      phone: null,
      photo: null,
    };
  },
  methods: {
  },
});
</script>

<style>
  body {
    font-family: 'Arial', sans-serif;
    background-color: #f8f9fa;
    margin: 0;
    padding: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
  }

  b-container {
    max-width: 600px;
    width: 100%;
  }

  form {
    background-color: #ffffff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }

  .form-group {
    margin-bottom: 20px;
  }

  label {
    font-weight: bold;
    display: block;
    margin-bottom: 8px;
  }

  input,
  select,
  b-form-file {
    width: 100%;
    padding: 8px;
    margin-top: 4px;
    margin-bottom: 8px;
    box-sizing: border-box;
    border: 1px solid #ced4da;
    border-radius: 4px;
    font-size: 16px;
  }

  input[type="file"] {
    cursor: pointer;
  }

  button {
    background-color: #007bff;
    color: #ffffff;
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
  }

  button:hover {
    background-color: #0056b3;
  }

  .alert {
    margin-bottom: 20px;
  }

  .alert ul {
    list-style: none;
    padding: 0;
  }

  .alert li {
    color: #721c24;
    background-color: #f8d7da;
    padding: 8px;
    margin-bottom: 8px;
    border-radius: 4px;
  }

  .alert b {
    font-weight: bold;
  }
</style>

