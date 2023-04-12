<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  data() {
    return {
      showButton: false,
    };
  },

  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },

  created() {
    window.addEventListener('scroll', this.handleScroll);
  },

  destroyed() {
    window.removeEventListener('scroll', this.handleScroll);
  },

  methods: {

    handleScroll() {

      if (window.pageYOffset > 100) {
        this.showButton = true;
      } else {
        this.showButton = false;
      }
    },

    scrollTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      });
    }
  }
}
</script>

<template>
  <AppHeader></AppHeader>
  <AppMain></AppMain>
  <AppFooter></AppFooter>
  <div>
    <button v-if="showButton" @click="scrollTop" class="back-to-top"><i class="fa-solid fa-arrow-up"></i></button>
  </div>
</template>

<style lang="scss" scoped>
.back-to-top {
  position: fixed;
  bottom: 20px;
  right: 140px;
  color: white;
  padding: 14px 18px;
  border: none;
  border-radius: 50%;
  cursor: pointer;
  transition: opacity 0.3s, transform 0.3s;
  background: linear-gradient(to right, #2ef41c, #00D9A6);

  i {
    font-size: 1.3em;
  }

  &:hover {
    opacity: 0.8;
    transform: scale(1.2);
  }
}
</style>

