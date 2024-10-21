<template>
  <div class="min-h-screen flex">
 

    <!-- Nội dung chính -->
    <div class="flex-grow ">
      <Header @toggle-menu="toggleNav" />
         <!-- Menu Drawer (Nav) -->
    <Nav :isOpen="isNavOpen" />
      <h1>Nội dung chính</h1>
    </div>
  </div>
</template>

<script>
import Nav from '../components/Nav.vue';
import Header from '../components/Header.vue';

export default {
  name: 'Home',
  components: {
    Nav,
    Header,
  },
  data() {
    return {
      isNavOpen: false, // Trạng thái mở/đóng của menu Nav
    };
  },
  methods: {
    toggleNav() {
      this.isNavOpen = !this.isNavOpen; // Đảo ngược trạng thái khi nhấn vào nút
    },
  },
};
</script>

<style scoped>
/* Các style bổ sung nếu cần */
</style>
