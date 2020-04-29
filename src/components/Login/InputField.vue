<template>
  <div>
    <p>{{inputName}}</p>
    <q-input
      color="teal"
      filled
      v-model="input"
      v-bind:type="inputType"
      v-bind:placeholder="placeHolder"
      v-bind:rules="requiredInput ? [val => !!val || 'Field is required'] : []"
    >
      <template v-if="inputType == 'password'" v-slot:append>
        <a class="text-warning forgotPass" @click="forgotPasswordHandler">Forgot Password ?</a>
      </template>
    </q-input>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component
export default class InputComponent extends Vue {
  @Prop({ type: String, required: true }) readonly inputType!:
    | "email"
    | "password";
  @Prop({ type: Boolean, default: false }) requiredInput!: boolean;

  input: string = "";

  get inputName(): string {
    let inputName = "Unnamed field";

    if (this.inputType == "email")
      inputName = "E-mail address: " + (this.requiredInput ? "*" : "");
    else if (this.inputType == "password")
      inputName = "Password: " + (this.requiredInput ? "*" : "");

    return inputName;
  }

  get placeHolder(): string {
    let placeHolder = "";

    if (this.inputType == "email")
      placeHolder = "Your email address (... @ ...)";

    return placeHolder;
  }

  forgotPasswordHandler() {
    console.log("TODO ForgotPasswordHandler");
  }
}
</script>

<style >
.forgotPass {
  font-size: 15px;  
  text-decoration: underline;
}
</style>
