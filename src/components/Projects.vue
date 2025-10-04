<script setup>
import { ref, onMounted } from 'vue';

const projects = ['lareii.github.io', 'siker.im', 'FdF', 'cub3D'];
const repos = ref([]);

onMounted(async () => {
  try {
    const response = await fetch('https://api.github.com/users/lareii/repos');
    const data = await response.json();

    // Ambil semua project yang cocok
    repos.value = data
      .filter(repo => projects.includes(repo.name))
      .sort((a, b) => b.stargazers_count - a.stargazers_count); // Optional: urutkan
  } catch (error) {
    console.error("Failed to fetch repos", error);
  }
});
</script>

<template>
  <div class="mb-2 font-black text-2xl">projects/</div>

  <div class="grid md:grid-cols-2 gap-2">
    <div v-if="!repos.length">projects could not be retrieved.</div>

    <!-- Manual box menggunakan <a> -->
    <a
      v-for="repo in repos"
      :key="repo.id"
      :href="repo.html_url"
      target="_blank"
      class="block px-4 py-3 bg-[#202020]/30 border border-[#504945] rounded-lg text-sm hover:bg-[#2a2a2a] transition"
    >
      <!-- Nama Repo -->
      <div class="font-bold text-lg" :class="{ 'line-through': repo.archived }">
        {{ repo.name }}
      </div>

      <!-- Deskripsi Repo -->
      <div class="text-gray-300">
        {{ repo.description || 'No description provided.' }}
      </div>

      <!-- Info Stars dan Forks -->
      <div class="mt-2 text-xs text-gray-500">
        ⭐ {{ repo.stargazers_count }} &nbsp;&nbsp;|&nbsp;&nbsp; 🍴 {{ repo.forks_count }}
      </div>
    </a>
  </div>
</template>
        <div>{{ repo.description }}</div>
      </div>
      <div class="flex mt-2 gap-5">
        <div>
          <font-awesome-icon :icon="['fas', 'star']" />
          {{ repo.stargazers_count }}
        </div>
        <div>
          <font-awesome-icon :icon="['fas', 'code-branch']" />
          {{ repo.forks_count }}
        </div>
      </div>
    </a>
  </div>
</template>
