<template>
	<div class="scanner">
		<qrcode-stream @detect="onDetect"></qrcode-stream>
	</div>
	<p>!----------------SCANNER COMPONENT DEBUG----------------!</p>
	<p v-if="content">{{ content }}</p>
</template>

<script setup lang="ts">
import { QrcodeStream } from 'vue-qrcode-reader'
import { ref } from "vue";
const onDetect = (ctx: object) => {
	content.value = ctx
}
const content = ref<object>({})
</script>

<style scoped>
.scanner {
	display: flex;
	justify-content: center;
	align-items: center;
	width: 40vh;
	height: 40vh;
}
</style>