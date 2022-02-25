<template>
<div class="app">
	<sidebar
	v-model:username="username"
	v-model:email="email"
	v-model:phone="phone"
	v-model:website="website"
	></sidebar>
	<home
	class="home"
	:username="username"
	:email="email"
	:phone="phone"
	:website="website"
	v-model:text="text"
	></home>
</div>
</template>

<script>
import Sidebar from './components/sidebar.vue'
import Home from './components/home.vue'

export default {
	name: 'app',
	components: {
		Sidebar,
		Home
	},
	data() {
		return {
			username: '',
			email: '',
			phone: '',
			website: '',
			text: ''
		}
	}
}
</script>

<style lang="scss">
* {
	margin: 0;
	padding: 0;
	color: #8a5082;
	box-sizing: border-box;
	font-weight: 700;
	font-family: 'anonymous pro';
}
button {
	border: none;
	border-radius: 5px;
	background-color: #8a5082;
	padding: 5px 10px;
	color: #ffffff;
	cursor: pointer;
}
input,
textarea {
	width: 100%;
	border: 1px solid #8a5082;
	border-radius: 5px;
	background-color: inherit;
	&:focus {
		outline: none;
	}
}
input {
	padding: 5px 10px;
}
textarea {
	padding: 10px;
	resize: none;
}
.app {
	display: flex;
	.home {
		flex: 1;
	}
}
</style>
