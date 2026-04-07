<script setup lang="ts">
import { computed, ref } from 'vue'
import profileImg from '@/assets/images/profile.png'
import portfolioPdf from '@/assets/portfolio.pdf'

type TabId = 'frequently' | 'favorites' | 'experienced' | 'values'

const activeTab = ref<TabId>('frequently')

interface Tech {
  name: string
  icon: string
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

const tabs: { id: TabId; label: string; icon: string }[] = [
  { id: 'frequently', label: '주력', icon: 'mdi:fire' },
  { id: 'favorites', label: '선호', icon: 'mdi:heart' },
  { id: 'experienced', label: '경험', icon: 'mdi:puzzle' },
  { id: 'values', label: '가치', icon: 'mdi:star' }
]

const stacksByTab: Record<TabId, Tech[]> = {
  frequently: frequentlyUsed,
  favorites,
  experienced,
  values
}

const currentStacks = computed(() => stacksByTab[activeTab.value])

const stats = [
  { label: '주력 스택', value: frequentlyUsed.length },
  { label: '애정 스택', value: favorites.length },
  { label: '경험 스택', value: experienced.length },
  { label: '핵심 가치', value: values.length }
]
</script>

<template>
  <div class="min-h-screen bg-[#f3e9dc] p-6 text-[#5e3023] font-sans">
    <div class="mx-auto max-w-6xl w-full grid gap-8 lg:grid-cols-[340px_1fr] lg:items-start">
      
      <!-- Left Sidebar -->
      <aside class="flex flex-col gap-6">
        <!-- Profile Card -->
        <div class="rounded-3xl border-2 border-[#c08552]/30 bg-white/60 backdrop-blur-md p-8 shadow-xl">
          <div class="mb-6 flex justify-between items-start">
            <span class="inline-flex items-center gap-2 rounded-full border border-[#c08552] bg-[#c08552]/10 px-3 py-1 text-xs font-bold text-[#c08552]">
              <span class="h-2 w-2 rounded-full bg-[#c08552] animate-pulse"></span>
              OPEN TO WORK
            </span>
          </div>

          <div class="mb-6 text-center">
            <img :src="profileImg" alt="Profile" class="mx-auto h-32 w-32 rounded-3xl object-cover border-4 border-[#f3e9dc] shadow-lg mb-4" />
            <h1 class="text-3xl font-extrabold text-[#5e3023]">VBKOROA</h1>
            <p class="mt-2 text-sm font-semibold tracking-widest text-[#c08552] uppercase">Backend Engineer</p>
          </div>

          <div class="w-12 h-1 bg-[#c08552] mx-auto rounded-full mb-6"></div>

          <p class="mb-8 text-center text-sm leading-relaxed text-[#5e3023]/80">
            사용자와 개발자가 동시에 만족할 수 있는, 안정적이고 확장 가능한 서비스를 만듭니다.
          </p>

          <div class="flex flex-col gap-3">
            <a href="mailto:yoojs0254@kakao.com" class="group flex items-center justify-between rounded-xl bg-[#c08552] px-4 py-3 text-white transition-all hover:bg-[#5e3023] shadow-md hover:shadow-lg">
              <span class="flex items-center gap-3 font-medium">
                <iconify-icon icon="mdi:email" width="20"></iconify-icon> Email
              </span>
              <iconify-icon icon="mdi:arrow-right" class="transition-transform group-hover:translate-x-1"></iconify-icon>
            </a>
            <a :href="portfolioPdf" target="_blank" class="group flex items-center justify-between rounded-xl border border-[#c08552] bg-white px-4 py-3 text-[#c08552] transition-all hover:bg-[#c08552] hover:text-white shadow-sm">
              <span class="flex items-center gap-3 font-medium">
                <iconify-icon icon="mdi:briefcase" width="20"></iconify-icon> Portfolio
              </span>
              <iconify-icon icon="mdi:arrow-top-right" class="transition-transform group-hover:translate-x-1 group-hover:-translate-y-1"></iconify-icon>
            </a>
          </div>
        </div>

        <!-- Stats Card -->
        <div class="grid grid-cols-2 gap-4">
          <div v-for="stat in stats" :key="stat.label" class="flex flex-col items-center justify-center rounded-3xl border-2 border-[#c08552]/40 bg-white p-5 text-center shadow-md transition-transform hover:-translate-y-1">
            <p class="text-3xl font-black text-[#5e3023]">{{ stat.value }}</p>
            <p class="mt-2 text-xs font-bold text-[#c08552] uppercase tracking-wide">{{ stat.label }}</p>
          </div>
        </div>
      </aside>

      <!-- Main Content -->
      <main class="rounded-3xl border-2 border-[#5e3023]/10 bg-white/60 backdrop-blur-md p-8 shadow-xl flex flex-col lg:sticky lg:top-6 lg:max-h-[calc(100vh-3rem)] overflow-y-auto overflow-x-hidden">
        <div class="mb-8 flex flex-col gap-4 sm:flex-row sm:items-center sm:justify-between shrink-0">
          <h2 class="text-2xl font-extrabold text-[#5e3023] flex items-center gap-2">
            <iconify-icon icon="mdi:code-braces" class="text-[#c08552]"></iconify-icon>
            Tech Stack
          </h2>
          
          <div class="w-full sm:w-auto flex gap-1 sm:gap-2 p-1 sm:p-1.5 rounded-2xl bg-[#f3e9dc] border border-[#5e3023]/10 shadow-inner overflow-x-auto">
            <button
              v-for="tab in tabs" :key="tab.id" @click="activeTab = tab.id"
              :class="[
                'flex-1 sm:flex-none flex items-center justify-center gap-1.5 px-2 py-2.5 sm:px-4 sm:py-2 rounded-xl text-[11px] sm:text-sm font-bold transition-all duration-300 whitespace-nowrap',
                activeTab === tab.id
                  ? 'bg-[#5e3023] text-white shadow-md transform sm:scale-105'
                  : 'text-[#5e3023]/60 hover:text-[#5e3023] hover:bg-white'
              ]"
            >
              <iconify-icon :icon="tab.icon" width="16"></iconify-icon>
              {{ tab.label }}
            </button>
          </div>
        </div>

        <div class="grid grid-cols-2 gap-4 sm:grid-cols-3 lg:grid-cols-4 content-start">
          <article
            v-for="(item, index) in currentStacks" :key="item.name"
            class="group flex flex-col items-center justify-center p-6 rounded-2xl border-2 border-transparent bg-white shadow-sm transition-all duration-300 hover:border-[#c08552] hover:shadow-lg hover:-translate-y-1 cursor-pointer animate-card-in"
            :style="{ animationDelay: `${index * 0.05}s` }"
          >
            <div class="mb-4 flex items-center justify-center text-4xl text-[#5e3023] transition-transform group-hover:scale-110 group-hover:text-[#c08552]">
              <iconify-icon :icon="item.icon" width="40" height="40"></iconify-icon>
            </div>
            <p class="text-sm font-bold text-[#5e3023] group-hover:text-[#c08552] text-center w-full truncate">{{ item.name }}</p>
          </article>
        </div>
      </main>
      
    </div>
  </div>
</template>

<style scoped>
:deep(iconify-icon) {
  display: inline-block;
}
</style>
