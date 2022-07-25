<template>
	<form
		@submit.prevent="$emit('howDay')"
		class="flex flex-col items-center justify-between"
	>
		<div class="flex flex-col items-center mb-5">
			<label class="mb-5 text-lg font-bold"
				>how many days you hit gym in 1 week</label
			>
			<input
				class="border-2 w-full h-10 text-lg bg-gray-50 border-purple-500 outline-none rounded"
				type="number"
			/>
		</div>
		<button class="text-white bg-purple-500 p-2 px-4 rounded text-xl">
			next
		</button>
	</form>
</template>
