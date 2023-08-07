<template>
  <div class="app">
    <h1 > 生日快乐 事事顺心</h1>
   <div class="greet">亲爱的，你是我生命中的动力和激情。愿你的生日充满无尽的幸福和满足，我会一直陪伴着你，为你创造更多美好的回忆。</div>
    <BirthdayCard
       :photos="photoList"
    />
    <audio controls :src="music" autoplay>
      Your browser does not support the audio element.
    </audio>
  </div>
</template>

<script>
import BirthdayCard from './BirthdayCard.vue';

export default {
  name: 'App',
  components: {
    BirthdayCard,
  },
  data() {
    return {
      music:'hbd.mp3',
      photoList: Array.from({ length: 40 }, (_, index) => `${index + 1}.jpg`),
    };
  },
};
</script>

<style scoped  >
.app {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #06799F;
  flex-direction: column;
}
audio{
  position: fixed;
  bottom: 10px;
}
h1{
  text-align: center;
  padding: 20px;
  font-family: Arial, sans-serif;
  position: fixed;
  top: 10px;
  color: #FFB400;

}
.greet{
  text-align: center;
  /* padding: 20px; */
  font-family: Arial, sans-serif;
  position: fixed;
  top: 120px;
  color: #d4e5fd;
  font-size: 25px;
  padding: 0 20px;
  font-weight: bolder;

}
@keyframes typing {
	from { width: 0 }
}

@keyframes caret {
	50% { border-right-color: transparent; }
}

h1 {
	font: bold 200% Consolas, Monaco, monospace;
/* 	width: 8.25em; */
	width: 16ch;
	white-space: nowrap;
	overflow: hidden;
	border-right: .05em solid;
	animation: typing 4s steps(15) infinite,
	           caret 1s steps(1) infinite;
}

</style>
