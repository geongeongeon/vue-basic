<template>
	<div>
		<h2>input Value</h2>
		<!-- <input type="text" v-model.lazy="inputValue" /> -->
		<!-- <input type="text" v-model.number="inputValue" /> -->
		<input type="text" v-model.trim="inputValue" />
		<!-- :value="inputValue" @input="event => {inputValue = event.target.value;}" -->
		<div>{{ inputValue }}</div>
		<div>{{ typeof inputValue }}</div>

		<h2>textarea value</h2>
		<textarea v-model="textareaValue"></textarea>
		<div>{{ textareaValue }}</div>
	</div>

	<h2>checkbox value</h2>
	<label for="checkbox">{{ checkboxValue }}</label>
	<input
		type="checkbox"
		id="checkbox"
		v-model="checkboxValue"
		true-value="Y"
		false-value="N"
	/>
	<!-- :checked="checkboxValue"
		@change="event => (checkboxValue = event.target.checked)" -->

	<h2>radio value</h2>
	<label>
		<input type="radio" name="type" value="O" v-model="radioValue" />
		<!-- :checked="radioValue === 'O'"@change="event => {radioValue = event.target.value;}" -->
		O형
	</label>
	<label>
		<input type="radio" name="type" value="A" v-model="radioValue" />
		A형
	</label>
	<div>{{ radioValue }}</div>

	<h2>select value</h2>
	<select v-model="selectValue">
		<option value="html">HTML 수업</option>
		<option value="css">CSS 수업</option>
		<option value="javascript">JavaScript 수업</option>
	</select>
	<div>{{ selectValue }}</div>

	<h3>checkbox values</h3>
	<label>
		<input type="checkbox" value="html" v-model="checkboxValues" />
		HTML
	</label>
	<label>
		<input type="checkbox" value="css" v-model="checkboxValues" />
		CSS
	</label>
	<label>
		<input type="checkbox" value="javascript" v-model="checkboxValues" />
		JavaScript
	</label>
	<div>{{ checkboxValues }}</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const inputValue = ref('');
		const textareaValue = ref('');
		const checkboxValue = ref('N');
		const checkboxValues = ref([]);
		const radioValue = ref('O');
		const selectValue = ref('html');

		return {
			inputValue,
			textareaValue,
			checkboxValue,
			radioValue,
			selectValue,
			checkboxValues,
		};
	},
};
</script>

<style lang="scss" scoped></style>
