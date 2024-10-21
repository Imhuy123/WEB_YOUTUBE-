<template>
  <div
    :class="[isOpen ? 'w-48' : 'w-16', isDarkMode ? 'bg-gray-900' : 'bg-slate-400']"
    class="text-white min-h-screen transition-all duration-300 ease-in-out p-4"
  >
    <div class="flex flex-col space-y-10">
      <!-- Trang Chủ -->
      <div class="flex items-center space-x-2">
        <i :class="isDarkMode ? 'text-white' : 'text-black'" class="bx bx-home-alt text-2xl"></i>
        <span v-if="isOpen">Trang Chủ</span>
      </div>

      <!-- Kênh Đăng Ký -->
      <div class="flex items-center space-x-2">
        <i :class="isDarkMode ? 'text-white' : 'text-black'" class="bx bxs-slideshow text-2xl"></i>
        <span v-if="isOpen">Kênh Đăng Ký</span>
      </div>

      <!-- Phim Bộ -->
      <div class="flex items-center space-x-2">
        <i :class="isDarkMode ? 'text-white' : 'text-black'" class="bx bx-movie text-2xl"></i>
        <span v-if="isOpen">Phim Bộ</span>
      </div>

      <!-- Cài Đặt -->
      <div class="flex items-center space-x-2">
        <i :class="isDarkMode ? 'text-white' : 'text-black'" class="bx bx-cog text-2xl"></i>
        <span v-if="isOpen">Cài Đặt</span>
      </div>

      <!-- NỘI DUNG THÊM KHI NAV MỞ -->
      <div v-if="isOpen">
        <div class="flex flex-col space-y-10">
          <!-- Phim Đã Xem -->
          <div class="flex items-center space-x-2">
            <i :class="isDarkMode ? 'text-white' : 'text-black'" class="fas fa-info-circle text-2xl"></i>
            <span>Phim Đã Xem</span>
          </div>

          <!-- Kênh đã thích -->
          <div class="flex items-center space-x-2">
            <i :class="isDarkMode ? 'text-white' : 'text-black'" class="bx bx-like text-2xl"></i>
            <span>Kênh đã thích</span>
          </div>

          <!-- Kênh Đăng Ký -->
          <div class="flex items-center space-x-2">
            <i :class="isDarkMode ? 'text-white' : 'text-black'" class="fas fa-sign-out-alt text-2xl"></i>
            <span>Kênh Đăng Ký</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Nav',
  props: {
    isOpen: {
      type: Boolean,
      default: false, // Thanh nav bắt đầu ở trạng thái đóng
    },
    isDarkMode: {
      type: Boolean,
      default: false, // Trạng thái Dark Mode
    }
  },
};
</script>

<style scoped>
/* Các style bổ sung nếu cần */
</style>
