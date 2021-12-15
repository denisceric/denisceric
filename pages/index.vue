<template>
  <div>
    <div ref="home" class="h-screen flex flex-col bg-secondary text-gray-300 relative">
      <!-- Navbar -->
      <div
        class="
          flex
          justify-between
          items-center
          border-b border-primary
          fixed
          w-full
          bg-secondary
          z-10
        "
      >
        <nuxt-link to="/" class="p-4 lg:p-8 hover:opacity-75"
          >Denis Ceric</nuxt-link
        >

        <button class="p-4 lg:hidden" @click="menuOpen = !menuOpen">
          <MenuIcon :open="menuOpen" />
        </button>

        <!-- Mobile menu -->
        <nav class="hidden lg:flex">
          <span class="p-8 hover:opacity-75 cursor-pointer" @click="scrollTo('home')">Home</span>
          <span class="p-8 hover:opacity-75 cursor-pointer" @click="scrollTo('projects')">Projects</span>
          <a class="p-8 bg-primary hover:bg-black" href="resume.pdf">Download resume</a>
        </nav>
      </div>

      <!-- Mobile menu -->
      <nav v-if="menuOpen" class="lg:hidden flex flex-col">
        <span class="p-4">Home</span>
        <span class="p-4">Projects</span>
        <span class="p-4">Download resume</span>
      </nav>

      <div
        class="
          m-auto
          bg-primary
          p-8
          xl:p-16
          flex flex-col
          items-center
          rounded-xl
        "
      >
        <span class="text-2xl lg:text-4xl xl:text-6xl">Hi, I'm Denis</span>
        <span class="mt-4 uppercase text-gray-400 lg:text-2xl xl:text-3xl"
          >Full-stack Developer</span
        >
      </div>
    </div>

    <div ref="projects" class="h-full flex flex-col bg-secondary text-gray-300 relative py-16">
      <div class="flex justify-center items-center border-b border-primary">
        <span class="p-4 lg:p-8 text-2xl">Projects</span>
      </div>

      <div class="container mx-auto border border-gray-700 p-2 mt-16">
        <div
          class="
            flex flex-col
            lg:flex-row
            flex-wrap
            justify-center
            items-center
          "
        >
          <img
            src="mailpool/analytics.png"
            class="p-4 w-96 flex-1 bg-primary"
          />
          <img src="mailpool/emails.png" class="p-4 w-96 flex-1 bg-primary" />
          <img src="mailpool/billing.png" class="p-4 w-96 flex-1 bg-primary" />
        </div>
        <div class="p-4 text-xl">
          <strong class="uppercase">Full-stack</strong>
          <p class="mt-4">
            The backend for this project was built with Python (Flask) and
            PostgresSQL (SQLAlchemy) and it is using websockets, multiprocessing and async
            concurrency.<br>
            Frontend was built using Vue and Tailwind. 
            Stripe was integrated to enable one-time purchases and monthly subscriptions.
            Various Google APIs were used also.
          </p>
        </div>
      </div>
      <div class="container mx-auto border border-gray-700 p-2 mt-16">
        <div
          class="
            flex flex-col
            lg:flex-row
            flex-wrap
            justify-center
            items-center
          "
        >
          <img
            src="movie-pickr/recommendations.png"
            class="p-4 w-96 flex-1 bg-primary"
          />
          <img src="movie-pickr/movie.png" class="p-4 w-96 flex-1 bg-primary" />
          <img src="movie-pickr/saved.png" class="p-4 w-96 flex-1 bg-primary" />
        </div>
        <div class="p-4 text-xl">
          <strong class="uppercase">Full-stack</strong>
          <p class="mt-4">
            This project is built using React Native and Redux, it is using Firebase for authentication.
          </p>
        </div>
      </div>
      <div class="container mx-auto border border-gray-700 p-2 mt-16">
        <div
          class="
            flex flex-col
            lg:flex-row
            flex-wrap
            justify-center
            items-center
          "
        >
          <img
            src="id/dashboard.png"
            class="p-4 w-96 flex-1 bg-primary"
          />
          <img src="id/idea.png" class="p-4 w-96 flex-1 bg-primary" />
          <img src="id/post.png" class="p-4 w-96 flex-1 bg-primary" />
        </div>
        <div class="p-4 text-xl">
          <strong class="uppercase">Front-end</strong>
          <p class="mt-4">
            This project is built using Vue and Tailwind and all functionalities were hand-made without using third-pary libraries.
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menuOpen: false
    }
  },

  methods: {
    scrollTo(ref) {
      this.$refs[ref].scrollIntoView({ behavior: 'smooth'});
    }
  }
}
</script>