<script setup>
import { ref } from "vue";
const isLogedIN = ref(true);
defineEmits(["showProgramForm"]);
</script>
<template>
	<nav
		class="w-full bg-purple-700 flex justify-end text-white h-10 items-center pr-2"
	>
		<div v-if="!isLogedIN">
			<RouterLink to="/" class="mr-3 text-white underline"
				>Login</RouterLink
			>
			<RouterLink class="text-white underline" to="/">Sign Up</RouterLink>
		</div>
		<div v-else>
			<button
				@click="$emit('showProgramForm')"
				class="bg-blue-500 p-1 rounded-sm hover:bg-blue-400"
			>
				Add New Program
			</button>
		</div>
	</nav>
</template>
