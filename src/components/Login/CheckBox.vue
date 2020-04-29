<template>
  <div class="checkBox">
    <q-checkbox v-model="isChecked" v-bind:label="label" />
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component
export default class CheckBox extends Vue {
  @Prop({ type: String, default: "default label" }) readonly label!: string;
  @Prop({ type: Boolean, default: false }) readonly active!: boolean;

  isChecked: boolean = this.active;
}
</script>

<style>
.checkBox {
  margin: 10px;
}
</style>
