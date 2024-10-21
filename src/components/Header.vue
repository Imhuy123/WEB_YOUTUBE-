<template>
  <div class="relative">
    <!-- Header -->
    <div :class="isDarkMode ? 'dark' : ''" class="flex justify-between items-center p-4 bg-white dark:bg-gray-900 text-black dark:text-white">
      <!-- Góc trái: Menu Icon và Logo -->
      <div class="flex items-center space-x-4">
        <!-- Menu Icon (Hamburger) -->
        <div @click="$emit('toggle-menu')" class="space-y-1 cursor-pointer">
          <div class="w-8 h-1 bg-black dark:bg-white"></div>
          <div class="w-8 h-1 bg-black dark:bg-white"></div>
          <div class="w-8 h-1 bg-black dark:bg-white"></div>
        </div>

        <!-- Logo VAA -->
        <div class="bg-blue-200 rounded-full px-6 py-2 text-white text-4xl font-bold">
          VAA
        </div>
      </div>

      <!-- Ở giữa: Thanh tìm kiếm -->
      <div class="flex-grow max-w-md mx-auto">
        <!-- Input tìm kiếm -->
        <div class="flex items-center">
          <input 
            type="text" 
            placeholder="tìm kiếm" 
            class="w-full py-2 px-4 border border-gray-300 rounded-full focus:outline-none"
          />
          <!-- Nút tìm kiếm -->
          <button class="ml-2 px-4 py-2 bg-yellow-400 rounded-full hover:bg-yellow-500 focus:outline-none">
            <i class="bx bx-search text-2xl"></i>
          </button>
        </div>
      </div>

      <!-- Góc phải: Các biểu tượng khác -->
      <div class="flex items-center space-x-4">
        <!-- Icon Video -->
        <button>
          <i class="bx bx-video text-4xl"></i>
        </button>

        <!-- Icon Bell -->
        <button>
          <i class="bx bx-bell text-4xl"></i>
        </button>

        <!-- Avatar tròn -->
        <button>
          <i class='bx bx-user-circle text-4xl'></i>
        </button>

        <!-- Nút chuyển đổi giữa chế độ tối và sáng -->
        <button @click="toggleTheme" class="ml-4 p-2">
          <i v-if="isDarkMode" class="bx bx-sun text-4xl"></i>
          <i v-else class="bx bx-moon text-4xl"></i>
        </button>
      </div>
    </div>

    <!-- Thanh Nav (Side Drawer) -->
    <div v-if="isNavOpen" class="fixed inset-y-0 left-0 w-64 bg-gray-800 text-white p-4 transition-transform transform">
      <div class="flex flex-col space-y-4">
        <div class="flex items-center space-x-2">
          <i class="bx bx-home text-xl"></i>
          <span>Trang Chủ</span>
        </div>
        <div class="flex items-center space-x-2">
          <i class="bx bx-play-circle text-xl"></i>
          <span>Kênh Đăng Ký</span>
        </div>
        <div class="flex items-center space-x-2">
          <i class="bx bx-movie-play text-xl"></i>
          <span>Phim Bộ</span>
        </div>
        <div class="flex items-center space-x-2">
          <i class="bx bx-user text-xl"></i>
          <span>Trang Cá Nhân</span>
        </div>
        <div class="flex items-center space-x-2">
          <i class="bx bx-cog text-xl"></i>
          <span>Cài Đặt</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import 'boxicons/css/boxicons.min.css'; // Import Boxicons

export default {
  name: 'Header',
  data() {
    return {
      isDarkMode: false, // Bắt đầu với chế độ sáng
      isNavOpen: false,  // Trạng thái mở/đóng thanh nav
    }
  },
  methods: {
    toggleTheme() {
      this.isDarkMode = !this.isDarkMode;
      if (this.isDarkMode) {
        document.documentElement.classList.add('dark'); // Thêm chế độ tối
      } else {
        document.documentElement.classList.remove('dark'); // Xóa chế độ tối
      }
    },
    toggleNav() {
      this.isNavOpen = !this.isNavOpen; // Mở hoặc đóng thanh nav
    }
  }
}
</script>

<style scoped>
/* Dark mode styles */
.dark {
  background-color: #1a202c; /* Dark background */
  color: #f7fafc; /* Light text */
}

/* Transition for nav drawer */
.transition-transform {
  transition: transform 0.3s ease-in-out;
}

.fixed {
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  z-index: 50;
}
</style>
