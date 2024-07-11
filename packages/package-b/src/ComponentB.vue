<script setup lang="ts">
import { ComponentA, BaseRow } from "package-a";
import { ref } from "vue";

type MyRow = BaseRow & { text: string };

defineProps<{
  propB: string;
}>();

const rows = ref<MyRow[]>([
  { value: "1", text: "one" },
  { value: "2", text: "two" },
]);
</script>

<template>
  <component-a :rows="rows" non-generic="something">
    <template v-slot="{ row }">{{ row.text }}</template>
  </component-a>
</template>

<style scoped></style>
