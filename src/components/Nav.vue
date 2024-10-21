<template>
  <div :class="isOpen ? 'w-64' : 'w-16'" class="bg-gray-800 text-white min-h-screen transition-all duration-300 ease-in-out p-4">
    <div class="flex flex-col space-y-4">
      <div class="flex items-center space-x-2">
        <i class="fas fa-home"></i>
        <span v-if="isOpen">Trang Chủ</span>
      </div>
      <div class="flex items-center space-x-2">
        <i class="fas fa-play"></i>
        <span v-if="isOpen">Kênh Đăng Ký</span>
      </div>
      <div class="flex items-center space-x-2">
        <i class="fas fa-film"></i>
        <span v-if="isOpen">Phim Bộ</span>
      </div>
      <div class="flex items-center space-x-2">
        <i class="fas fa-user"></i>
        <span v-if="isOpen">Trang Cá Nhân</span>
      </div>
      <div class="flex items-center space-x-2">
        <i class="fas fa-cog"></i>
        <span v-if="isOpen">Cài Đặt</span>
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
  },
};
</script>

<style scoped>
/* Các style bổ sung nếu cần */
</style>
