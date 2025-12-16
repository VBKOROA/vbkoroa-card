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
  { name: 'Go', icon: 'devicon:go' },
  { name: 'Vue.js', icon: 'devicon:vuejs' },
  { name: 'React', icon: 'material-icon-theme:react' },
  { name: 'MyBatis', icon: 'mdi:sql-query' },
  { name: 'MariaDB', icon: 'devicon:mariadb' },
  { name: 'PostgreSQL', icon: 'devicon:postgresql' },
  { name: 'Redis', icon: 'devicon:redis' },
  { name: 'RabbitMQ', icon: 'devicon:rabbitmq' },
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
    <div class="w-full max-w-4xl my-4">
      <!-- Hero Card -->
      <div class="bg-gradient-to-br from-slate-950 to-black rounded-2xl border border-white/20 shadow-2xl overflow-hidden mb-8">
        <!-- Header Gradient -->
        <div class="h-20 sm:h-32 bg-gradient-to-r from-slate-900 via-black to-slate-900 relative overflow-hidden border-b border-white/10">
          <div class="absolute inset-0">
            <!-- Animated blur elements -->
            <div class="absolute w-96 h-96 bg-gradient-to-br from-white to-slate-400 rounded-full -top-40 -left-32 blur-3xl opacity-30 animate-pulse"></div>
            <div class="absolute w-80 h-80 bg-gradient-to-tl from-slate-300 to-white rounded-full -bottom-40 -right-40 blur-3xl opacity-25 animate-pulse animation-delay-1000"></div>
            <div class="absolute w-72 h-72 bg-slate-200 rounded-full top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 blur-2xl opacity-15"></div>
          </div>
        </div>

        <!-- Profile Content -->
        <div class="px-4 sm:px-8 py-6 sm:py-12 relative z-10">
          <div class="flex flex-col sm:flex-row items-start justify-between gap-4 sm:gap-6 mb-6 sm:mb-8">
            <div class="flex items-center gap-4 sm:gap-6 w-full sm:w-auto">
              <!-- Avatar Circle with Image -->
              <div class="w-20 sm:w-24 h-20 sm:h-24 rounded-full bg-white flex items-center justify-center shadow-lg -mt-8 sm:-mt-12 overflow-hidden border-4 border-black flex-shrink-0">
                <img :src="profileImg" alt="프로필" class="w-full h-full object-cover" />
              </div>
              <!-- Name and Title -->
              <div class="flex-1">
                <h1 class="text-2xl sm:text-4xl font-black text-white mb-1 sm:mb-2">
                  VBKOROA
                </h1>
                <p class="text-cyan-300 text-sm sm:text-lg font-semibold">백엔드 개발자</p>
              </div>
              <!-- Contact Links (모바일에서만 표시) -->
              <div class="flex gap-2 sm:hidden items-start">
                <a 
                  href="mailto:yoojs0254@kakao.com"
                  class="flex flex-col items-center gap-0.5 px-2 py-1.5 bg-slate-900/50 border border-white/20 rounded-lg hover:border-white/50 hover:bg-white/10 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 text-slate-300 hover:text-white group"
                >
                  <iconify-icon icon="mdi:email" width="20" class="group-hover:scale-110 transition-transform"></iconify-icon>
                </a>
                <a 
                  href="https://www.notion.so/2b19541fdc3080bd90b7f835e1d185cb?source=copy_link"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="flex flex-col items-center gap-0.5 px-2 py-1.5 bg-slate-900/50 border border-white/20 rounded-lg hover:border-white/50 hover:bg-white/10 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 text-slate-300 hover:text-white group"
                >
                  <iconify-icon icon="mdi:briefcase" width="20" class="group-hover:scale-110 transition-transform"></iconify-icon>
                </a>
              </div>
            </div>
            <!-- Contact Links (태블릿 이상에서는 우측) -->
            <div class="hidden sm:flex gap-3 items-start">
              <a 
                href="mailto:yoojs0254@kakao.com"
                class="flex flex-col items-center gap-0.5 px-3 py-2 bg-slate-900/50 border border-white/20 rounded-xl hover:border-white/50 hover:bg-white/10 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 text-slate-300 hover:text-white group"
              >
                <iconify-icon icon="mdi:email" width="24" class="group-hover:scale-110 transition-transform"></iconify-icon>
                <span class="text-xs font-semibold">이메일</span>
              </a>
              <a 
                href="https://www.notion.so/2b19541fdc3080bd90b7f835e1d185cb?source=copy_link"
                target="_blank"
                rel="noopener noreferrer"
                class="flex flex-col items-center gap-0.5 px-3 py-2 bg-slate-900/50 border border-white/20 rounded-xl hover:border-white/50 hover:bg-white/10 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 text-slate-300 hover:text-white group"
              >
                <iconify-icon icon="mdi:briefcase" width="24" class="group-hover:scale-110 transition-transform"></iconify-icon>
                <span class="text-xs font-semibold">포트폴리오</span>
              </a>
            </div>
          </div>

          <!-- Description -->
          <p class="text-slate-300 text-center text-sm sm:text-base max-w-2xl mx-auto mb-6 sm:mb-8 leading-relaxed">
            사용자와 개발자가 모두 즐거운, 견고하고 확장 가능한 서비스를 만듭니다. 시간이 지나도 가치가 남는 코드를 추구합니다.
          </p>

          <!-- Tab Navigation -->
          <div class="flex flex-wrap gap-2 justify-center mb-6 sm:mb-8">
            <button
              @click="activeTab = 'frequently'"
              :class="[
                'px-2 sm:px-4 py-1.5 sm:py-2 rounded-lg font-semibold transition-all duration-300 text-xs sm:text-sm',
                activeTab === 'frequently'
                  ? 'bg-white text-black shadow-lg'
                  : 'bg-slate-800/50 text-slate-300 border border-white/20 hover:bg-slate-700/50'
              ]"
            >
              <iconify-icon icon="mdi:fire" class="inline mr-2"></iconify-icon>
              주력
            </button>
            <button
              @click="activeTab = 'favorites'"
              :class="[
                'px-2 sm:px-4 py-1.5 sm:py-2 rounded-lg font-semibold transition-all duration-300 text-xs sm:text-sm',
                activeTab === 'favorites'
                  ? 'bg-white text-black shadow-lg'
                  : 'bg-slate-800/50 text-slate-300 border border-white/20 hover:bg-slate-700/50'
              ]"
            >
              <iconify-icon icon="mdi:heart" class="inline mr-2"></iconify-icon>
              선호
            </button>
            <button
              @click="activeTab = 'experienced'"
              :class="[
                'px-2 sm:px-4 py-1.5 sm:py-2 rounded-lg font-semibold transition-all duration-300 text-xs sm:text-sm',
                activeTab === 'experienced'
                  ? 'bg-white text-black shadow-lg'
                  : 'bg-slate-800/50 text-slate-300 border border-white/20 hover:bg-slate-700/50'
              ]"
            >
              <iconify-icon icon="mdi:puzzle" class="inline mr-2"></iconify-icon>
              경험
            </button>
            <button
              @click="activeTab = 'values'"
              :class="[
                'px-2 sm:px-4 py-1.5 sm:py-2 rounded-lg font-semibold transition-all duration-300 text-xs sm:text-sm',
                activeTab === 'values'
                  ? 'bg-white text-black shadow-lg'
                  : 'bg-slate-800/50 text-slate-300 border border-white/20 hover:bg-slate-700/50'
              ]"
            >
              <iconify-icon icon="mdi:star" class="inline mr-2"></iconify-icon>
              가치
            </button>
          </div>

          <!-- Tech Stack Display -->
          <div class="transition-all duration-500">
            <div v-if="activeTab === 'frequently'" class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-2 sm:gap-4">
              <div
                v-for="(tech, index) in frequentlyUsed"
                :key="tech.name"
                :style="{ animationDelay: `${index * 0.08}s` }"
                class="group bg-slate-900/50 border border-white/20 rounded-lg sm:rounded-xl p-3 sm:p-4 hover:border-white/50 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 cursor-pointer transform hover:scale-105 animate-card-in"
              >
                <div class="flex flex-col items-center gap-2 sm:gap-3">
                  <iconify-icon :icon="tech.icon" width="28" class="sm:w-8 text-slate-300 group-hover:text-white transition-colors"></iconify-icon>
                  <p class="text-slate-200 font-semibold text-center text-xs sm:text-sm">{{ tech.name }}</p>
                </div>
              </div>
            </div>

            <div v-else-if="activeTab === 'favorites'" class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-2 sm:gap-4">
              <div
                v-for="(tech, index) in favorites"
                :key="tech.name"
                :style="{ animationDelay: `${index * 0.08}s` }"
                class="group bg-slate-900/50 border border-white/20 rounded-lg sm:rounded-xl p-3 sm:p-4 hover:border-white/50 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 cursor-pointer transform hover:scale-105 animate-card-in"
              >
                <div class="flex flex-col items-center gap-2 sm:gap-3">
                  <iconify-icon :icon="tech.icon" width="28" class="sm:w-8 text-slate-300 group-hover:text-white transition-colors"></iconify-icon>
                  <p class="text-slate-200 font-semibold text-center text-xs sm:text-sm">{{ tech.name }}</p>
                </div>
              </div>
            </div>

            <div v-else-if="activeTab === 'experienced'" class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-2 sm:gap-4">
              <div
                v-for="(tech, index) in experienced"
                :key="tech.name"
                :style="{ animationDelay: `${index * 0.08}s` }"
                class="group bg-slate-900/50 border border-white/20 rounded-lg sm:rounded-xl p-3 sm:p-4 hover:border-white/50 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 cursor-pointer transform hover:scale-105 animate-card-in"
              >
                <div class="flex flex-col items-center gap-2 sm:gap-3">
                  <iconify-icon :icon="tech.icon" width="28" class="sm:w-8 text-slate-300 group-hover:text-white transition-colors"></iconify-icon>
                  <p class="text-slate-200 font-semibold text-center text-xs sm:text-sm">{{ tech.name }}</p>
                </div>
              </div>
            </div>

            <div v-else-if="activeTab === 'values'" class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-2 sm:gap-4">
              <div
                v-for="(value, index) in values"
                :key="value.name"
                :style="{ animationDelay: `${index * 0.08}s` }"
                class="group bg-slate-900/50 border border-white/20 rounded-lg sm:rounded-xl p-3 sm:p-4 hover:border-white/50 hover:shadow-lg hover:shadow-white/10 transition-all duration-300 cursor-pointer transform hover:scale-105 animate-card-in"
              >
                <div class="flex flex-col items-center gap-2 sm:gap-3">
                  <iconify-icon :icon="value.icon" width="28" class="sm:w-8 text-slate-300 group-hover:text-white transition-colors"></iconify-icon>
                  <p class="text-slate-200 font-semibold text-center text-xs sm:text-sm">{{ value.name }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Footer Stats -->
      <div class="grid grid-cols-2 sm:grid-cols-4 gap-2 sm:gap-4">
        <div class="bg-slate-950 border border-white/20 rounded-lg sm:rounded-xl p-3 sm:p-4 text-center">
          <p class="text-lg sm:text-2xl font-black text-white">
            {{ frequentlyUsed.length }}
          </p>
          <p class="text-slate-400 text-xs mt-1 sm:mt-2 font-semibold">주력 스택</p>
        </div>
        <div class="bg-slate-950 border border-white/20 rounded-lg sm:rounded-xl p-3 sm:p-4 text-center">
          <p class="text-lg sm:text-2xl font-black text-white">
            {{ favorites.length }}
          </p>
          <p class="text-slate-400 text-xs mt-1 sm:mt-2 font-semibold">애정 스택</p>
        </div>
        <div class="bg-slate-950 border border-white/20 rounded-lg sm:rounded-xl p-3 sm:p-4 text-center">
          <p class="text-lg sm:text-2xl font-black text-white">
            {{ experienced.length }}
          </p>
          <p class="text-slate-400 text-xs mt-1 sm:mt-2 font-semibold">경험 스택</p>
        </div>
        <div class="bg-slate-950 border border-white/20 rounded-lg sm:rounded-xl p-3 sm:p-4 text-center">
          <p class="text-lg sm:text-2xl font-black text-white">
            {{ values.length }}
          </p>
          <p class="text-slate-400 text-xs mt-1 sm:mt-2 font-semibold">핵심 가치</p>
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
