<template>
<div class="sidebar">
	<input
	:value="username"
	@input="usernameHandler"
	placeholder="username"
	type="text"
	>
	<input
	:value="email"
	@input="emailHandler"
	placeholder="email"
	type="text"
	>
	<input
	:value="phone"
	@input="phoneHandler"
	placeholder="phone"
	type="text"
	>
	<input
	:value="website"
	@input="websiteHandler"
	placeholder="website"
	type="text"
	>
</div>
</template>

<script>
export default {
	name: 'sidebar',
	props: {
		username: String,
		email: String,
		phone: String,
		website: String
	},
	methods: {
		usernameHandler(e) {
			this.$emit('update:username', e.target.value)
		},
		emailHandler(e) {
			this.$emit('update:email', e.target.value)
		},
		phoneHandler(e) {
			this.$emit('update:phone', e.target.value)
		},
		websiteHandler(e) {
			this.$emit('update:website', e.target.value)
		},
	}
}
</script>

<style lang="scss" scoped>
.sidebar {
	width: 20vw;
	height: 100vh;
	display: flex;
	padding: 10px;
	row-gap: 10px;
	flex-direction: column;
	background-color: #ff7b89;
}
</style>
