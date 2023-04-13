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
  <div class="right-absolute-item">
    <div class="item"><i class="fa-brands fa-chrome"></i>Browse Demos</div>
    <div class="item"><i class="fa-solid fa-bag-shopping"></i>Buy Now!</div>
    <div class="item"><i class="fa-solid fa-file-export"></i>Export Section</div>
  </div>
</template>

<style lang="scss" scoped>
@use "../src/scss/variables" as *;

.right-absolute-item {
  display: flex;
  flex-direction: column;
  gap: 6px;
  position: fixed;
  right: 0;
  top: 40%;
  color: white;
  font-size: 0.8em;

  i {
    padding-right: 6px;
    font-size: 1.2em;
  }

  .item {
    border-radius: 10px 0 0 10px;
    padding: 11px 40px 11px 20px;
    margin-right: -20px;
    background-color: rgba(0, 0, 0, 0.5);
    cursor: pointer;
    transition: all 0.4s ease-in-out;
    font-weight: 300;

    &:hover {
      background-color: rgb(0, 98, 251);
      transform: translateX(-20px);
    }
  }
}

.back-to-top {
  position: fixed;
  bottom: 30px;
  right: 40px;
  color: white;
  padding: 14px 18px;
  border: none;
  border-radius: 50%;
  cursor: pointer;
  transition: opacity 0.3s, transform 0.3s;
  background: linear-gradient(to right, $secondary-color, $primary-color);

  i {
    font-size: 1.3em;
  }

  &:hover {
    opacity: 0.8;
    transform: scale(1.2);
  }
}
</style>

