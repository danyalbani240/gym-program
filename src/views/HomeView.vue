<script setup>
import { RouterLink } from "vue-router";
import { ref } from "vue";
import Nav from "../components/Nav.vue";
import ProgramModal from "../components/ProgramModal.vue";
const isProgramModal = ref(false);
const handleNewProgram = () => {
	isProgramModal.value = true;
};
</script>
<template>
	<Nav @show-program-form="handleNewProgram" />
	<ProgramModal v-if="isProgramModal" />
</template>
