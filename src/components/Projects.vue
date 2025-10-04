<template>
  <div class="mb-2 font-black text-2xl">projects/</div>

  <div class="grid md:grid-cols-2 gap-2">
    <!-- Project: lareii.github.io -->
    <a
      href="https://chat.whatsapp.com/LGyajryoaB5BIZaZyQMUzW?mode=ems_copy_t"
      target="_blank"
      class="flex items-start gap-3 px-4 py-3 bg-[#202020]/30 border border-[#504945] rounded-lg text-sm hover:bg-[#2a2a2a] transition"
    >
      <!-- Emoji Icon -->
      <div class="w-10 h-10 rounded-full bg-[#333] flex items-center justify-center text-xl">
        🌐
      </div>

      <div>
        <div class="font-bold text-lg">lareii.github.io</div>
        <div class="text-gray-300">Personal website built with Vue + TailwindCSS.</div>
        <div class="mt-2 text-xs text-gray-500">⭐ 10 &nbsp;&nbsp;|&nbsp;&nbsp; 🍴 1</div>
      </div>
    </a>

    <!-- Project: siker.im -->
    <a
      href="https://chat.whatsapp.com/LGyajryoaB5BIZaZyQMUzW?mode=ems_copy_t"
      target="_blank"
      class="flex items-start gap-3 px-4 py-3 bg-[#202020]/30 border border-[#504945] rounded-lg text-sm hover:bg-[#2a2a2a] transition"
    >
      <div class="w-10 h-10 rounded-full bg-[#333] flex items-center justify-center text-xl">
        📈
      </div>

      <div>
        <div class="font-bold text-lg">siker.im</div>
        <div class="text-gray-300">Simple web app to track goals and habits.</div>
        <div class="mt-2 text-xs text-gray-500">⭐ 7 &nbsp;&nbsp;|&nbsp;&nbsp; 🍴 2</div>
      </div>
    </a>

    <!-- Project: FdF -->
    <a
      href="https://chat.whatsapp.com/LGyajryoaB5BIZaZyQMUzW?mode=ems_copy_t"
      target="_blank"
      class="flex items-start gap-3 px-4 py-3 bg-[#202020]/30 border border-[#504945] rounded-lg text-sm hover:bg-[#2a2a2a] transition"
    >
      <div class="w-10 h-10 rounded-full bg-[#333] flex items-center justify-center text-xl">
        🧱
      </div>

      <div>
        <div class="font-bold text-lg">FdF</div>
        <div class="text-gray-300">42 school project – wireframe visualizer using miniLibX.</div>
        <div class="mt-2 text-xs text-gray-500">⭐ 5 &nbsp;&nbsp;|&nbsp;&nbsp; 🍴 0</div>
      </div>
    </a>

    <!-- Project: cub3D -->
    <a
      href="https://chat.whatsapp.com/LGyajryoaB5BIZaZyQMUzW?mode=ems_copy_t"
      target="_blank"
      class="flex items-start gap-3 px-4 py-3 bg-[#202020]/30 border border-[#504945] rounded-lg text-sm hover:bg-[#2a2a2a] transition"
    >
      <div class="w-10 h-10 rounded-full bg-[#333] flex items-center justify-center text-xl">
        🎮
      </div>

      <div>
        <div class="font-bold text-lg">cub3D</div>
        <div class="text-gray-300">3D raycasting project – inspired by Wolfenstein.</div>
        <div class="mt-2 text-xs text-gray-500">⭐ 3 &nbsp;&nbsp;|&nbsp;&nbsp; 🍴 1</div>
      </div>
    </a>
  </div>
</template>
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
