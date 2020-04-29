<template>
  <q-btn unelevated v-bind:color='btnColor' size="md" v-bind:label='label' @click="signIn"/>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component
export default class SignInSocial extends Vue {
  @Prop({ type: String, default: "" }) readonly color!: string;
  @Prop({ type: String, default: "Google" }) readonly socialNetwork!: "Google" | "Facebook";

  get btnColor(): string {
    if (this.color == "") {
      switch (this.socialNetwork) {
        case "Facebook":
          return "indigo-8"
      
        case "Google":
          return "red-6"
      }
    }
    return this.color
  }

  get label(): string {
    return  "Sign in with " + this.socialNetwork 
  }

  signIn() {
    console.log("signing In with " + this.socialNetwork)
  }
}
</script>
