<template>
  <section class="main">
    <div class="about">
      <div class="container mx-auto">
        <h1 class="text-center text-4xl pt-8 pb-8">Who Am I?</h1>
        <div class="md:flex">
          <div class="flex-none w-full md:w-2/5">
            <!-- <img class="profile rounded-md" src="~/assets/me.jpg" alt="Jordan Smith" title="Jordan S" width="225" height="275"> -->
            <nuxt-img 
              class="profile rounded-md" 
              format="webp" 
              quality="90" 
              src="/me.jpg" 
              height="275" 
              width="225" 
            />
          </div>
          <div class="flex-none md:w-3/5 text-xl m-8 md:m-0">
            <p class="mb-4"> Hello, My name is Jordan Smith.</p>
            <p class="my-4">I am a Software Engineer with a focus on the front end and working knowledge of the back end.</p>
            <p class="my-4">I currently build web based applications using  VueJS/Nuxt as a Javascript Framework, PHP, and Cloud Services (AWS, Google Cloud).</p>
            <p class="my-4">Currently, I am getting more familiar with cloud platform services and working on getting more AWS Certifications. I am also improving my skills with Nuxt on top of Vue, and learning a little Python along the way as well as a third language.</p>
            <p>When I am not working on apps I also build and maintain static and E-commerce websites (Shopify, Woocommerce).</p>
            <div class="pt-4 pb-8 sm:text-center md:text-left">
              <button @click="getModal">
                <font-awesome-icon 
                  class="text-5xl pr-4 text-teal-800" 
                  icon="fa-solid fa-envelope" 
                />
              </button>
              <a 
                href="https://www.linkedin.com/in/jordan-smith-b1068483/"
                target="_blank"
              >
                <font-awesome-icon 
                  class="text-5xl pr-4 text-teal-800" 
                  icon="fa-brands fa-linkedin" 
                /> 
              </a> 
              <a 
                href="https://github.com/jaysmit158"
                target="_blank"
              >
                <font-awesome-icon 
                  class="text-5xl pr-4 text-teal-800" 
                  icon="fa-brands fa-github" 
                />
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <EmailModal/>
  </section>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      
    }
  },
  methods: {
    getModal() {

    }
  }
}
</script>
<style>
  .main {
    min-height: calc(100vh - 64px);
  }
  .profile {
    max-width: 300px;
    margin: auto;
  }
</style>