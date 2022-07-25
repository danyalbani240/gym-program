<script setup>
import { XCircleIcon } from "@heroicons/vue/outline";
import BaseForm from "./BaseForm.vue";
import { ref } from "vue";
defineEmits(["close"]);
function handleHowDay() {
	console.log(5);
}
const component = BaseForm;
</script>
<template>
	<div class="fixed bg-gray-100 left-0 top-0 w-full h-screen p-5">
		<button @click="$emit('close')">
			<XCircleIcon class="w-8 text-blue-400" />
		</button>

		<div>
			<component @how-day="handleHowDay" :is="component" />
		</div>
	</div>
</template>
