<template>
  <dialog 
		id="contactModal" 
		:open="show === true ? true : false"
		class="top-0 left-0 w-full h-full absolute bg-slate-100/75"
		@click.self="$emit('close', false)"
	>
		<div class="formWrapper">
			<button class="float-right" @click="close"> Close &times; </button>
			<div class="clear-both"></div>
			<form 
				id="emailForm" 
				name="Contact Me - FFE Portfolio" 
				method="POST" 
				data-netlify="true"
				data-netlify-recaptcha="true"
				data-netlify-honeypot="bot-field"
				class="bg-white"
			>
				<div class="flex">
					<label for="name" class="flex-auto">Your Name</label>
					<input id="name" class="flex-auto border border-teal-800" name="name" type="text" required />
				</div>
				<div class="flex">
					<label for="eAddress">Email</label>
					<input id="eAddress" name="email" class="flex-auto border border-teal-800" type="email" required />
				</div>
				<label for="message">Your Message</label>
				<div class="hidden">
					<input name="bot-field" />
				</div>
				<div class="flex">
					<textarea 
						id="message" 
						name="message" 
						rows="4" 
						class="flex-auto border border-teal-800" 
						required
					></textarea>
				</div>
				<div data-netlify-recaptcha="true" class="recap-block"></div>
				<button type="submit" class="bg-teal-800 text-white w-full">Submit</button>
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