<template>
  <nav class="w-full p-6 border-outset border-b-2 border-black Header">
    <div class="flex items-center justify-between">

      <!-- Mobile toggle -->
      <div>
        <button @click="drawer">
          <svg 
            class="h-8 w-8 fill-current text-black"
            fill="none" stroke-linecap="round" 
            stroke-linejoin="round" stroke-width="2" 
            viewBox="0 0 24 24" stroke="currentColor">
              <path d="M4 6h16M4 12h16M4 18h16"></path>
          </svg>
        </button>
      </div>

      <!-- Navbar -->
      <div class="hidden md:block">
      </div>

      <!-- Dark Background Transition -->
      <transition
        enter-class="opacity-0"
        enter-active-class="ease-out transition-medium"
        enter-to-class="opacity-100"
        leave-class="opacity-100"
        leave-active-class="ease-out transition-medium"
        leave-to-class="opacity-0"
      >
        <div @keydown.esc="isOpen = false" v-show="isOpen" class="z-10 fixed inset-0 transition-opacity">
            <div @click="isOpen = false" class="absolute inset-0 bg-black opacity-50" tabindex="0"></div>
        </div>
      </transition>

      <!-- Drawer Menu -->
      <aside class="p-5 transform top-0 left-0 w-64 bg-white fixed h-full overflow-auto ease-in-out transition-all duration-300 z-30" :class="isOpen ? 'translate-x-0' : '-translate-x-full'">
        
        <div class="close">
          <button class="absolute top-0 right-0 mt-4 mr-4" @click="isOpen = false">
            <svg 
              class="w-6 h-6"
              fill="none" stroke-linecap="round" 
              stroke-linejoin="round" stroke-width="2"
              viewBox="0 0 24 24" stroke="currentColor">
              <path d="M6 18L18 6M6 6l12 12"></path>
            </svg>
          </button>
        </div>

        <ul class="divide-y font-sans">
          <li><button @click="navigate('/')" class="my-4 inline-block text-black">Home</button></li>
          <li><button @click="navigate('/about-us')" class="my-4 inline-block text-black">About Tottenham</button></li>
          <li><button @click="navigate('/Players')" class="my-4 inline-block text-black">Players</button></li>
          <li><button @click="navigate('/chants')" class="my-4 inline-block text-black">chants</button></li>
        </ul>

      </aside>

      <!-- Header logo -->
      <div>
        <nuxt-link to="/">
        <h1><img src="https://www.linkpicture.com/q/tottenham.png" class="logo"/> </h1>
        </nuxt-link>
      </div>

      <!-- Header logo -->
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false
    };
  },
  methods: {
    drawer() {
      this.isOpen = !this.isOpen;
    },
    navigate(path) {
        this.$router.push(path);
        this.drawer();
    }
  },
  watch: {
    isOpen: {
      immediate: true,
      handler(isOpen) {
        if (process.client) {
          if (isOpen) document.body.style.setProperty("overflow", "hidden");
          else document.body.style.removeProperty("overflow");
        }
      }
    }
  },
  mounted() {
    document.addEventListener("keydown", e => {
      if (e.keyCode == 27 && this.isOpen) this.isOpen = false;
    });
  }
};
</script>
<style>
.logo {
    height: 50px;
}
.Header {
    background-color: rgb(239,239,239);
}
</style>