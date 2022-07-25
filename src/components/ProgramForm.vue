<script setup>
import { XIcon, PlusIcon } from "@heroicons/vue/outline";
import { ref } from "vue";

const exersicePrograms = ref([{}]);
const exersiceName = ref("");
const exersiceReps = ref();
const setNewProgramItem = () => {
	console.log(exersiceName.value, exersiceReps.value);
};
</script>
<template>
	<form class="" @submit.prevent="">
		<div class="flex items-center" v-for="item in exersicePrograms">
			<input
				class="border-2 p-1 placeholder:text-gray-500 w-8/12 h-10 text-base bg-gray-50 border-purple-500 outline-none rounded"
				type="text"
				placeholder="Enter your exercise name"
				v-model="exersiceName"
			/>
			<p><XIcon class="w-5 mx-3" /></p>
			<input
				class="border-2 p-1 placeholder:text-gray-500 w-2/12 h-10 text-lg bg-gray-50 border-purple-500 outline-none rounded"
				type="number"
				placeholder="Reps"
				v-model="exersiceReps"
			/>
			<button class="text-white bg-purple-500 p-2 ml-2 rounded">
				<plusIcon @click="setNewProgramItem" class="w-5" />
			</button>
		</div>
	</form>
</template>
