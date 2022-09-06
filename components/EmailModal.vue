<template>
  <dialog 
		id="contactModal" 
		:open="show === true ? true : false"
		class="top-0 left-0 w-full h-full absolute bg-slate-100/75"
	>
		<div class="formWrapper">
			<button class="float-right" @click="close"> Close &times; </button>
			<form 
				id="emailForm" 
				name="Contact Me - FFE Portfolio" 
				method="POST" 
				data-netlify="true"
				data-netlify-recaptcha="true"
				data-netlify-honeypot="bot-field"
				class="bg-white"
			>
				<div class="clear"></div>
				<label for="name">Your Name</label>
				<input id="name" name="name" type="text" required />
				<label for="eAddress">Email</label>
				<input id="eAddress" name="email" type="email" required />
				<label for="message">Your Message</label>
				<div class="hidden">
					<input name="bot-field">
				</div>
				<div data-netlify-recaptcha="true" class="recap-block"></div>
				<textarea id="message" name="message" rows="4" required></textarea>
				<button type="submit">Submit</button>
			</form>
		</div>
	</dialog>
</template>

<script>
export default {
  name: 'Home',
  props: {
		show: Boolean
	},
  data() {
    return {
    }
  },
  methods: {
		close() {
			this.show = false;
			this.$emit('close', this.show);
		},
    getModal() {
      this.show = true;
    }
  }
}
</script>
<style>
	.formWrapper {
		position: absolute;
		left: 50%;
		top: 50%;
		max-width: 300px;
		width: 95%;
		transform: translate(-50%, -50%);
	}
</style>