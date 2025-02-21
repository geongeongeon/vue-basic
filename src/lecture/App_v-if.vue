<template>
	<div>
		<h2 v-if="visible">Hello Vue3!</h2>
		<h2 v-else>false</h2>
		<button v-on:click="visible = !visible">toggle</button>
		<hr />
		<h2 v-if="type === 'A'">A</h2>
		<h2 v-else-if="type === 'B'">B</h2>
		<h2 v-else-if="type === 'C'">C</h2>
		<h2 v-else>NULL</h2>
		<button v-on:click="type = 'A'">A</button>
		<button v-on:click="type = 'B'">B</button>
		<button v-on:click="type = 'C'">C</button>
		<button v-on:click="type = 'NULL'">NULL</button>
		<hr />
		<template v-if="visible">
			<h1>Title</h1>
			<p>Paragraph 1</p>
			<p>Paragraph 2</p>
		</template>
		<hr />
		<h1 v-show="show">v-show</h1>
		<button v-on:click="show = !show">toggle</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const visible = ref(false);
		const type = ref('A');
		const show = ref(true);

		return {
			visible,
			type,
			show,
		};
	},
};
</script>

<style lang="scss" scoped></style>
