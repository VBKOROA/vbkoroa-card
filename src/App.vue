<script setup lang="ts">
import { ref } from 'vue'
import profileImg from '@/assets/images/profile.png'

const activeTab = ref<'frequently' | 'favorites' | 'experienced' | 'values'>('frequently')

interface Tech {
  name: string
  icon: string
  category?: string
}

const frequentlyUsed: Tech[] = [
  { name: 'Java', icon: 'mdi:language-java' },
  { name: 'Spring Boot', icon: 'simple-icons:spring' },
  { name: 'JPA', icon: 'mdi:database' },
  { name: 'QueryDSL', icon: 'mdi:code-braces-box' },
  { name: 'MySQL', icon: 'mdi:database' },
  { name: 'JUnit5', icon: 'mdi:test-tube' },
  { name: 'Mockito', icon: 'mdi:puzzle' },
  { name: 'Docker', icon: 'mdi:docker' }
]

const favorites: Tech[] = [
  { name: 'C#', icon: 'mdi:language-csharp' },
  { name: '.NET Core', icon: 'simple-icons:dotnet' },
  { name: 'EF Core', icon: 'mdi:database-outline' }
]

const experienced: Tech[] = [
  { name: 'Python', icon: 'mdi:language-python' },
  { name: 'FastAPI', icon: 'mdi:lightning-bolt' },
  { name: 'Vue.js', icon: 'mdi:vuejs' },
  { name: 'React', icon: 'mdi:react' },
  { name: 'MariaDB', icon: 'mdi:database' },
  { name: 'PostgreSQL', icon: 'mdi:database-outline' },
  { name: 'Redis', icon: 'mdi:lightning-bolt-circle' },
  { name: 'Elasticsearch', icon: 'mdi:magnify' },
  { name: 'AWS', icon: 'mdi:aws' },
  { name: 'OpenFeign', icon: 'mdi:network-outline' },
  { name: 'Tailwind CSS', icon: 'mdi:tailwind' },
  { name: 'K6', icon: 'mdi:speedometer' },
  { name: 'Postman', icon: 'mdi:send' }
]

const values: Tech[] = [
  { name: 'UX', icon: 'mdi:palette-advanced' },
  { name: 'Performance', icon: 'mdi:rocket' },
  { name: 'Stability', icon: 'mdi:shield-check' },
  { name: 'DX', icon: 'mdi:heart-multiple' }
]
</script>

<template>
  <div class="min-h-screen bg-gradient-to-br from-black via-slate-900 to-black flex items-center justify-center p-4">
    <!-- Main Card Container -->
    <div class="w-full max-w-4xl">
      <!-- Hero Card -->
      <div class="bg-gradient-to-br from-slate-950 to-black rounded-2xl border border-white/20 shadow-2xl overflow-hidden mb-8">
        <!-- Header Gradient -->
        <div class="h-32 bg-gradient-to-r from-slate-900 via-black to-slate-900 relative overflow-hidden border-b border-white/10">
          <div class="absolute inset-0">
            <!-- Animated blur elements -->
            <div class="absolute w-96 h-96 bg-gradient-to-br from-white to-slate-400 rounded-full -top-40 -left-32 blur-3xl opacity-30 animate-pulse"></div>
            <div class="absolute w-80 h-80 bg-gradient-to-tl from-slate-300 to-white rounded-full -bottom-40 -right-40 blur-3xl opacity-25 animate-pulse animation-delay-1000"></div>
            <div class="absolute w-72 h-72 bg-slate-200 rounded-full top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 blur-2xl opacity-15"></div>
          </div>
        </div>

        <!-- Profile Content -->
        <div class="px-8 py-12 relative z-10">
          <div class="flex items-end gap-6 mb-8">
            <!-- Avatar Circle with Image -->
            <div class="w-24 h-24 rounded-full bg-white flex items-center justify-center shadow-lg -mt-16 overflow-hidden border-4 border-black">
              <img :src="profileImg" alt="Profile" class="w-full h-full object-cover" />
            </div>
            <!-- Name and Title -->
            <div>
              <h1 class="text-4xl font-black text-white mb-2">
                VBKOROA
              </h1>
              <p class="text-cyan-300 text-lg font-semibold">Backend Developer</p>
            </div>
          </div>

          <!-- Description -->
          <p class="text-slate-300 text-center max-w-2xl mx-auto mb-8 leading-relaxed">
            Passionate about building robust, scalable applications with exceptional user experience and developer experience. Crafting code that stands the test of time.
          </p>

          <!-- Tab Navigation -->
          <div class="flex flex-wrap gap-2 justify-center mb-8">
            <button
              @click="activeTab = 'frequently'"
              :class="[
                'px-4 py-2 rounded-lg font-semibold transition-all duration-300 text-sm',
                activeTab === 'frequently'
                  ? 'bg-white text-black shadow-lg'
                  : 'bg-slate-800/50 text-slate-300 border border-white/20 hover:bg-slate-700/50'
              ]"
            >
              <iconify-icon icon="mdi:fire" class="inline mr-2"></iconify-icon>
              Frequently Used
            </button>
            <button
              @click="activeTab = 'favorites'"
              :class="[
                'px-4 py-2 rounded-lg font-semibold transition-all duration-300 text-sm',
                activeTab === 'favorites'
                  ? 'bg-white text-black shadow-lg'
                  : 'bg-slate-800/50 text-slate-300 border border-white/20 hover:bg-slate-700/50'
              ]"
            >
              <iconify-icon icon="mdi:heart" class="inline mr-2"></iconify-icon>
              Favorites
            </button>
            <button
              @click="activeTab = 'experienced'"
              :class="[
                'px-4 py-2 rounded-lg font-semibold transition-all duration-300 text-sm',
                activeTab === 'experienced'
                  ? 'bg-white text-black shadow-lg'
                  : 'bg-slate-800/50 text-slate-300 border border-white/20 hover:bg-slate-700/50'
              ]"
            >
              <iconify-icon icon="mdi:briefcase" class="inline mr-2"></iconify-icon>
              Experienced
            </button>
            <button
              @click="activeTab = 'values'"
              :class="[
                'px-4 py-2 rounded-lg font-semibold transition-all duration-300 text-sm',
                activeTab === 'values'
                  ? 'bg-white text-black shadow-lg'
                  : 'bg-slate-800/50 text-slate-300 border border-white/20 hover:bg-slate-700/50'
              ]"
            >
              <iconify-icon icon="mdi:star" class="inline mr-2"></iconify-icon>
              Core Values
            </button>
          </div>

          <!-- Tech Stack Display -->
          <div class="transition-all duration-500">
            <div v-if="activeTab === 'frequently'" class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4">
              <div
                v-for="(tech, index) in frequentlyUsed"
                :key="tech.name"
                :style="{ animationDelay: `${index * 0.08}s` }"
                class="group bg-slate-900/50 border border-white/20 rounded-xl p-4 hover:border-white/50 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 cursor-pointer transform hover:scale-105 animate-card-in"
              >
                <div class="flex flex-col items-center gap-3">
                  <iconify-icon :icon="tech.icon" width="32" class="text-slate-300 group-hover:text-white transition-colors"></iconify-icon>
                  <p class="text-slate-200 font-semibold text-center text-sm">{{ tech.name }}</p>
                </div>
              </div>
            </div>

            <div v-else-if="activeTab === 'favorites'" class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4">
              <div
                v-for="(tech, index) in favorites"
                :key="tech.name"
                :style="{ animationDelay: `${index * 0.08}s` }"
                class="group bg-slate-900/50 border border-white/20 rounded-xl p-4 hover:border-white/50 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 cursor-pointer transform hover:scale-105 animate-card-in"
              >
                <div class="flex flex-col items-center gap-3">
                  <iconify-icon :icon="tech.icon" width="32" class="text-slate-300 group-hover:text-white transition-colors"></iconify-icon>
                  <p class="text-slate-200 font-semibold text-center text-sm">{{ tech.name }}</p>
                </div>
              </div>
            </div>

            <div v-else-if="activeTab === 'experienced'" class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4">
              <div
                v-for="(tech, index) in experienced"
                :key="tech.name"
                :style="{ animationDelay: `${index * 0.08}s` }"
                class="group bg-slate-900/50 border border-white/20 rounded-xl p-4 hover:border-white/50 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 cursor-pointer transform hover:scale-105 animate-card-in"
              >
                <div class="flex flex-col items-center gap-3">
                  <iconify-icon :icon="tech.icon" width="32" class="text-slate-300 group-hover:text-white transition-colors"></iconify-icon>
                  <p class="text-slate-200 font-semibold text-center text-sm">{{ tech.name }}</p>
                </div>
              </div>
            </div>

            <div v-else-if="activeTab === 'values'" class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4">
              <div
                v-for="(value, index) in values"
                :key="value.name"
                :style="{ animationDelay: `${index * 0.08}s` }"
                class="group bg-slate-900/50 border border-white/20 rounded-xl p-4 hover:border-white/50 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 cursor-pointer transform hover:scale-105 animate-card-in"
              >
                <div class="flex flex-col items-center gap-3">
                  <iconify-icon :icon="value.icon" width="32" class="text-slate-300 group-hover:text-white transition-colors"></iconify-icon>
                  <p class="text-slate-200 font-semibold text-center text-sm">{{ value.name }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Footer Stats -->
      <div class="grid grid-cols-4 gap-4 mb-8">
        <div class="bg-slate-950 border border-white/20 rounded-xl p-4 text-center">
          <p class="text-2xl font-black text-white">
            {{ frequentlyUsed.length }}
          </p>
          <p class="text-slate-400 text-xs mt-1 font-semibold">PREFERRED</p>
        </div>
        <div class="bg-slate-950 border border-white/20 rounded-xl p-4 text-center">
          <p class="text-2xl font-black text-white">
            {{ favorites.length }}
          </p>
          <p class="text-slate-400 text-xs mt-1 font-semibold">FAVORITES</p>
        </div>
        <div class="bg-slate-950 border border-white/20 rounded-xl p-4 text-center">
          <p class="text-2xl font-black text-white">
            {{ experienced.length }}
          </p>
          <p class="text-slate-400 text-xs mt-1 font-semibold">EXPERIENCED</p>
        </div>
        <div class="bg-slate-950 border border-white/20 rounded-xl p-4 text-center">
          <p class="text-2xl font-black text-white">
            {{ values.length }}
          </p>
          <p class="text-slate-400 text-xs mt-1 font-semibold">VALUES</p>
        </div>
      </div>

      <!-- Contact Footer -->
      <div class="flex flex-col items-center gap-4 text-center">
        <div class="flex gap-6 justify-center">
          <a 
            href="mailto:yoojs0254@kakao.com"
            class="flex items-center gap-2 px-6 py-3 bg-slate-950 border border-white/20 rounded-xl hover:border-white/50 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 text-slate-300 hover:text-white group"
          >
            <iconify-icon icon="mdi:email" width="20" class="group-hover:text-white"></iconify-icon>
            <span class="font-semibold">Email</span>
          </a>
          <a 
            href="https://www.notion.so/2b19541fdc3080bd90b7f835e1d185cb?source=copy_link"
            target="_blank"
            rel="noopener noreferrer"
            class="flex items-center gap-2 px-6 py-3 bg-slate-950 border border-white/20 rounded-xl hover:border-white/50 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 text-slate-300 hover:text-white group"
          >
            <iconify-icon icon="mdi:briefcase-document" width="20" class="group-hover:text-white"></iconify-icon>
            <span class="font-semibold">Portfolio</span>
          </a>
        </div>
        <p class="text-slate-500 text-sm">© 2025 vbkoroa. All rights reserved.</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
:deep(iconify-icon) {
  display: inline-block;
}
</style>
