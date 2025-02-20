<template>
	<div>
		<h2>{{ teacher.name }}</h2>
		<h3>강의가 있습니까?</h3>
		<!-- <p>{{ teacher.lectures.length > 0 ? '네' : '아니오' }}</p> -->
		<p>{{ hasLecture }}</p>
		<p>{{ hasLecture }}</p>
		<p>{{ existLecture() }}</p>
		<p>{{ existLecture() }}</p>
		<button v-on:click="counter++">Counter: {{ counter }}</button>
		<h2>이름</h2>
		<p>{{ fullName }}</p>
	</div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
	setup() {
		const teacher = reactive({
			name: '홍길동',
			lectures: ['HTML/CSS', 'JavaScript', 'Vue3'],
		});

		const hasLecture = computed(() => {
			console.log('computed');
			return teacher.lectures.length > 0 ? '네' : '아니오';
		});

		const existLecture = () => {
			console.log('method');
			return teacher.lectures.length > 0 ? '네' : '아니오';
		};

		const counter = ref(0);

		const firstName = ref('홍');
		const lastName = ref('길동');
		const fullName = computed({
			get() {
				return firstName.value + ' ' + lastName.value;
			},
			set(value) {
				console.log('value: ', value);
				console.log(value.split(' '));
				[firstName.value, lastName.value] = value.split(' ');
			},
		});
		console.log('console: ', fullName.value);
		fullName.value = '김 철수';

		return {
			teacher,
			hasLecture,
			existLecture,
			counter,
			fullName,
		};
	},
};
</script>

<style lang="scss" scoped></style>
