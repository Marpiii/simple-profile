<script setup>
import Header from './components/Header.vue';
import Uses from './components/Uses.vue';
import Projects from './components/Projects.vue';
import Footer from './components/Footer.vue';
import { onMounted } from 'vue';
</script>

<template>
  <div class="sm:pt-20 max-w-screen-lg mx-auto p-5 relative">
    <div class="z-0 absolute -mt-10 right-0 text-[10rem] opacity-10 select-none">✨</div>
    <div class="relative mb-10"><Header /></div>
    <div class="mb-10"><Uses /></div>
    <div class="z-0 absolute mt-10 text-[10rem] opacity-10 select-none">👨‍💻</div>
    <div class="relative mb-10"><Projects /></div>
    <Footer />
  </div>

  <!-- 🎵 Background Music -->
  <audio id="bg-music" autoplay hidden></audio>
</template>

<script setup>
onMounted(() => {
  const playlist = [
    '/music/Coba Lagi.mp3',
    '/music/Paling Sabi.mp3',
    '/music/Tenxi - Berubah (Official Music Video).mp3',
    '/music/Tenxi, suisei & Jemsii - mejikuhibiniu (Official Music Video).mp3'
  ]

  let current = 0;
  const music = document.getElementById('bg-music');

  const playNext = () => {
    music.src = playlist[current];
    music.play().catch(() => {});
    current = (current + 1) % playlist.length; // loop playlist
  };

  music.addEventListener('ended', playNext);

  const initPlay = () => {
    playNext();
    window.removeEventListener('click', initPlay);
    window.removeEventListener('scroll', initPlay);
  };

  window.addEventListener('click', initPlay, { once: true });
  window.addEventListener('scroll', initPlay, { once: true });
});
</script>
