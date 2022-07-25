<script setup>
import { XCircleIcon } from "@heroicons/vue/outline";
import BaseForm from "./BaseForm.vue";
import ProgramForm from "./ProgramForm.vue";
import { ref, shallowRef } from "vue";
//emits

defineEmits(["close"]);
// refs
const component = shallowRef(BaseForm);
const daysOfProgram = ref();
//methods
function handleHowDay(value) {
	daysOfProgram.value = value;
	changeComponent("next");
}
const changeComponent = (side) => {
	if (side === "next") {
		component.value = ProgramForm;
	}
};
</script>
<template>
	<div class="fixed bg-gray-100 left-0 top-0 w-full h-screen p-5">
		<button @click="$emit('close')">
			<XCircleIcon class="w-8 text-blue-400" />
		</button>

		<div class="p-2">
			<Transition name="fade" mode="out-in">
				<component
					@how-day="handleHowDay"
					:day-amount="daysOfProgram"
					:is="component"
				/>
			</Transition>
		</div>
	</div>
</template>
<style>
.fade-enter-active,
.fade-leave-active {
	transition: all 0.5s ease;
}

.fade-enter-from {
	opacity: 0;
	transform: translateX(50px);
}

.fade-leave-to {
	opacity: 0;
	transform: translateX(-100px);
}
</style>
