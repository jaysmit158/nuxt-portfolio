<template>
  <dialog 
		id="contactModal" 
		:open="show === true ? true : false"
		class="top-0 left-0 w-full h-full fixed bg-slate-100/75 z50"
		@click.self="$emit('close')"
	>
		<div class="formWrapper absolute">
			<button class="float-right font-bold green text-2xl" @click="close"> Close &times; </button>
			<div class="clear-both"></div>
			<form 
				id="emailForm" 
				name="Contact Me - FFE Portfolio" 
				method="POST" 
				data-netlify="true"
				data-netlify-recaptcha="true"
				data-netlify-honeypot="bot-field"
				class="bg-white p-4 rounded"
			>
				<div class="mb-2">
					<label for="name" class="w-full">Your Name:</label>
					<input id="name" class="w-full border border-teal-800" name="name" type="text" placeholder=" Your Name..." />
				</div>
				<div class="mb-2">
					<label for="eAddress" class="w-full">Email:</label>
					<input id="eAddress" name="email" class="w-full border border-teal-800" type="email" placeholder=" Your Email..." />
				</div>
				<div>
					<label for="message" class="w-full">Your Message:</label>
					<textarea 
						id="message" 
						name="message" 
						rows="4" 
						class="w-full border border-teal-800"
						placeholder=" Your Message..." 
					></textarea>
				</div>
				<div class="hidden">
					<input name="bot-field" />
				</div>
				<div data-netlify-recaptcha="true" class="recap-block m-2"></div>
				<button type="submit" class="bg-teal-800 mt-4 text-white w-full p-1">Submit</button>
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
		this.$emit('close');
	}
  }
}
</script>
<style>
	.green {
		color: #125d59;
	}
	.formWrapper {
		left: 50%;
		top: 50%;
		max-width: 450px;
		width: 95%;
		transform: translate(-50%, -50%);
	}
</style>