<script setup lang="ts">
import QrScanner from "@/components/QrScanner.vue";
import {ref} from "vue";
const onDetect = (ctx: object) => {
	content.value = ctx
}
const content = ref<object>()
</script>

<template>
  <main>
	<QrScanner/>
  </main>
</template>
