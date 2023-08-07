<template>
  <div class="birthday-card">
    <transition name="fade" mode="out-in">

     <img :key="currentPhoto" :src="currentPhoto" alt="Birthday Person" class="responsive-image" />
    </transition>

  </div>
</template>

<script>
export default {
  name: 'BirthdayCard',
  props: {
    // greeting: String,
    photos: Array,

  },
  data() {
    return {
      currentPhotoIndex: 0,
    };
  },
  computed: {
    currentPhoto() {
      return this.photos[this.currentPhotoIndex];
    },
  },
  mounted() {
    this.startPhotoLoop();
  },
  methods: {
    startPhotoLoop() {
      setInterval(() => {
        this.currentPhotoIndex = (this.currentPhotoIndex + 1) % this.photos.length;
      }, 2500); // 每 5 秒切换一张照片
    },
  },
};
</script>

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
.birthday-card {
  text-align: center;
  padding: 0 20px;
  transform: translateY(100px);
  font-family: Arial, sans-serif;
}

.responsive-image {
  max-width: 100%;
  /* 图片最大宽度为屏幕宽度 */
  height: auto;
  /* 保持宽高比例 */
}

h1 {
  font-size: 20px;
  color: #ff8973;
}

audio {
  position: fix;
  bottom: 0px;
}
</style>
