<template>
  <q-btn unelevated v-bind:color='color' size="md" class="full-width" v-bind:label='label' @click="signIn"/>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component
export default class SignIn extends Vue {
  @Prop({ type: String, default: "Login" }) readonly label!: string;
  @Prop({ type: String, default: "warning" }) readonly color!: string;

  signIn() {
    console.log("signing In")
  }
}
</script>
