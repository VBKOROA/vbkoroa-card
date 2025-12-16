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
  { name: 'Java', icon: 'devicon:java' },
  { name: 'Spring Boot', icon: 'logos:spring-icon' },
  { name: 'JPA', icon: 'devicon:hibernate' },
  { name: 'QueryDSL', icon: 'mdi:sql-query' },
  { name: 'MySQL', icon: 'logos:mysql' },
  { name: 'JUnit5', icon: 'devicon:junit' },
  { name: 'Mockito', icon: 'grommet-icons:test' },
  { name: 'Docker', icon: 'material-icon-theme:docker' }
]

const favorites: Tech[] = [
  { name: 'C#', icon: 'material-icon-theme:csharp' },
  { name: '.NET Core', icon: 'devicon:dotnetcore' },
  { name: 'EF Core', icon: 'devicon:entityframeworkcore' }
]

const experienced: Tech[] = [
  { name: 'TypeScript', icon: 'devicon:typescript' },
  { name: 'NestJS', icon: 'devicon:nestjs' },
  { name: 'Python', icon: 'material-icon-theme:python' },
  { name: 'FastAPI', icon: 'devicon:fastapi' },
  { name: 'Vue.js', icon: 'devicon:vuejs' },
  { name: 'React', icon: 'material-icon-theme:react' },
  { name: 'MariaDB', icon: 'devicon:mariadb' },
  { name: 'PostgreSQL', icon: 'devicon:postgresql' },
  { name: 'Redis', icon: 'devicon:redis' },
  { name: 'Elasticsearch', icon: 'devicon:elasticsearch' },
  { name: 'AWS', icon: 'skill-icons:aws-light' },
  { name: 'OpenFeign', icon: 'clarity:thin-client-line' },
  { name: 'Tailwind CSS', icon: 'vscode-icons:file-type-tailwind' },
  { name: 'K6', icon: 'devicon:k6' },
  { name: 'Postman', icon: 'devicon:postman' },
  { name: 'JSP', icon: 'vscode-icons:file-type-jsp' },
  { name: 'Thymeleaf', icon: 'devicon:thymeleaf' }
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
          <div class="flex items-start justify-between gap-6 mb-8">
            <div class="flex items-end gap-6">
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
            <!-- Contact Links -->
            <div class="flex gap-3 items-start">
              <a 
                href="mailto:yoojs0254@kakao.com"
                class="flex flex-col items-center gap-1 px-3 py-2 bg-slate-900/50 border border-white/20 rounded-xl hover:border-white/50 hover:bg-white/10 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 text-slate-300 hover:text-white group"
              >
                <iconify-icon icon="mdi:email" width="24" class="group-hover:scale-110 transition-transform"></iconify-icon>
                <span class="text-xs font-semibold">Email</span>
              </a>
              <a 
                href="https://www.notion.so/2b19541fdc3080bd90b7f835e1d185cb?source=copy_link"
                target="_blank"
                rel="noopener noreferrer"
                class="flex flex-col items-center gap-1 px-3 py-2 bg-slate-900/50 border border-white/20 rounded-xl hover:border-white/50 hover:bg-white/10 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 text-slate-300 hover:text-white group"
              >
                <iconify-icon icon="mdi:briefcase" width="24" class="group-hover:scale-110 transition-transform"></iconify-icon>
                <span class="text-xs font-semibold">Portfolio</span>
              </a>
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
      <div class="grid grid-cols-4 gap-4">
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
    </div>
  </div>
</template>

<style scoped>
:deep(iconify-icon) {
  display: inline-block;
}
</style>
