<template>
  <div
		id="contactModal" 
		class="top-0 left-0 w-full h-full fixed bg-slate-100/75 z50"
		@click.self="close"
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
						<label for="eName" class="w-full">Your Name:</label>
						<input id="eName" class="w-full border border-teal-800" name="name" type="text" placeholder="Your Name..." v-model="nameVal" />
					</div>
					<div class="mb-2">
						<label for="eAddress" class="w-full">Email:</label>
						<input id="eAddress" name="email" class="w-full border border-teal-800" type="email" placeholder="Your Email..." v-model="emailVal" />
					</div>
					<div>
						<label for="message" class="w-full">Your Message:</label>
						<textarea 
							id="message" 
							name="message" 
							rows="4" 
							class="w-full border border-teal-800"
							placeholder="Your Message..." 
							v-model="messageVal"
						></textarea>
					</div>
					<div class="hidden">
						<input name="bot-field" />
					</div>
					<div data-netlify-recaptcha="true" class="recap-block m-2"></div>
					<button type="submit" class="bg-teal-800 mt-4 text-white w-full p-1">Submit</button>
				</form> 
		</div>
	</div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
		nameVal: '',
		emailVal: '',
		messageVal: ''
    }
  },
  methods: {
	close() {
		console.log("close")
		this.$emit('close');
	}
  },
  watch: {
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