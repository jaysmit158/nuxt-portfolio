<template>
  <dialog 
		id="contactModal" 
		:open="show === true ? true : false"
		class="top-0 left-0 w-full h-full absolute bg-slate-100/75"
	>
		<form 
			id="emailForm" 
			name="Contact Me - FFE Portfolio" 
			method="POST" 
			data-netlify="true"
			class="bg-white"
		>
			<button class="float-right" @click="close"> Close &times; </button>
			<div class="clear"></div>
			<label for="name">Your Name</label>
			<input id="name" type="text" required />
			<label for="eAddress">Email</label>
			<input id="eAddress" type="email" required />
			<label for="message">Your Message</label>
			<textarea id="message" rows="4"></textarea>
			<button type="submit">Submit</button>
		</form>
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
	#contactModal {
		/* background: rgba(0, 0, 0, 0.2); */
	}
	#emailForm {
		position: absolute;
		left: 50%;
		top: 50%;
		max-width: 300px;
		width: 95%;
		transform: translate(-50%, -50%);
	}
</style>