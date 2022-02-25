<template>
<div class="home">
	<div class="home__buttons">
		<button
		@click="usernameHandler"
		>username</button>
		<button
		@click="emailHandler"
		>email</button>
		<button
		@click="phoneHandler"
		>phone</button>
		<button
		@click="websiteHandler"
		>website</button>
	</div>
	<textarea
	:value="text"
	@input="textHandler"
	></textarea>
</div>
</template>

<script>
export default {
	name: 'home',
	props: {
		username: String,
		email: String,
		phone: String,
		website: String,
		text: String
	},
	methods: {
		textHandler(e) {
			this.$emit('update:text', e.target.value)
		},
		usernameHandler() {
			this.$emit('update:text', this.addUsername)
		},
		emailHandler() {
			this.$emit('update:text', this.addEmail)
		},
		phoneHandler() {
			this.$emit('update:text', this.addPhone)
		},
		websiteHandler() {
			this.$emit('update:text', this.addWebsite)
		}
	},
	computed: {
		addUsername() {
			return this.text + ` ${this.username} `
		},
		addEmail() {
			return this.text + ` ${this.email} `
		},
		addPhone() {
			return this.text + ` ${this.phone} `
		},
		addWebsite() {
			return this.text + ` ${this.website} `
		}
	}
}
</script>

<style lang="scss" scoped>
.home {
	padding: 10px;
	&__buttons {
		display: flex;
		align-items: center;
		column-gap: 10px;
		margin-bottom: 10px;
	}
	textarea {
		height: 20vh;
	}
}
</style>
