<template>
  <div class="justify-center items-center window-height row">
    <div class="q-pa-md">
      <div class="row justify-center">
        <h4>Login</h4>
      </div>
      <div class="row">
        <q-card class="q-pa-md">
          <div class="column">
            <q-form class="q-gutter-md">
              <input-field inputType="email" requiredInput></input-field>
              <input-field inputType="password" requiredInput></input-field>
              <check-box label="Stay signed in"></check-box>
              <sign-in></sign-in>
              <register></register>
              <template>
                <sign-in-social socialNetwork="Google"></sign-in-social>
                <sign-in-social socialNetwork="Facebook"></sign-in-social>
              </template>
            </q-form>
          </div>
        </q-card>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import InputField from "components/Login/InputField.vue";
import CheckBox from "components/Login/CheckBox.vue";
import SignIn from "components/Login/SignIn.vue";
import Register from "components/Login/Register.vue";
import SignInSocial from "components/Login/SignInSocial.vue";

export default {
  name: "Login",
  components: { InputField, CheckBox, SignIn, Register, SignInSocial }
};
</script>

<style>
.q-card {
  width: 450px;
}
</style>