<template>
  <div class="row justify-center">
    <p class="text-grey-6">
      Don't have an account yet?
      <a href="/register">Register.</a>
    </p>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component
export default class Register extends Vue {}
</script>

<style>
p,
a {
  font-weight: bold;
  color: inherit;
}
</style>