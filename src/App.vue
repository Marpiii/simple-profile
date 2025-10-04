<script setup>
import Header from './components/Header.vue';
import Uses from './components/Uses.vue';
import Projects from './components/Projects.vue';
import Footer from './components/Footer.vue';
import { onMounted, ref } from 'vue';

const audioRef = ref(null);
const isPlaying = ref(false);

onMounted(() => {
  const playlist = [
    '/music/Coba-Lagi.mp3',
    '/music/Paling-Sabi.mp3',
    '/music/Tenxi-Berubah.mp3',
    '/music/Tenxi-suisei-Jemsii-mejikuhibiniu.mp3'
  ];

  let index = 0;
  const audio = audioRef.value;

  const playNext = () => {
    audio.src = playlist[index];
    audio.play().catch(() => {});
    index = (index + 1) % playlist.length;
  };

  audio.addEventListener('ended', playNext);

  const startPlay = () => {
    playNext();
    isPlaying.value = true;
  };

  // simpan function agar bisa dipanggil dari tombol
  window.__startMusic = startPlay;
});
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

  <!-- Tombol play -->
  <button
    v-if="!isPlaying"
    @click="window.__startMusic()"
    class="fixed bottom-5 right-5 bg-green-500 text-white px-4 py-2 rounded-full shadow-lg hover:bg-green-600 transition"
  >
    ▶️ Play Music
  </button>

  <!-- 🎧 Musik Latar -->
  <audio ref="audioRef" autoplay hidden></audio>
</template>
