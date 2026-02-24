<script setup lang="ts">
import { ref } from 'vue'
import { useRoute } from 'vue-router'
import { Menu, X, ArrowRight, Facebook, Linkedin, Code, MapPin, Phone, Mail, Home, Info, Layers, Briefcase, BookOpen, Send } from 'lucide-vue-next'

const route = useRoute()
const isMenuOpen = ref(false)

const menuItems = [
  { name: '首頁', path: '/', icon: Home },
  { name: '關於我們', path: '/about', icon: Info },
  { name: '服務項目', path: '/services', icon: Layers },
  { name: '工程實績', path: '/projects', icon: Briefcase },
  { name: 'EPOXY 專欄', path: '/epoxy', icon: BookOpen },
  { name: '聯絡我們', path: '/contact', icon: Send },
]
</script>

<template>
  <div class="min-h-screen bg-slate-50 text-slate-900 font-sans selection:bg-yellow-600 selection:text-white">
    <!-- Top Bar -->
    <div class="bg-slate-900 text-slate-400 text-[11px] py-1.5 px-4 hidden md:block border-b border-slate-800">
      <div class="max-w-7xl mx-auto flex justify-between items-center font-mono">
        <div class="flex gap-6">
          <span class="flex items-center gap-2 hover:text-white transition-colors cursor-pointer">
            <Phone :size="12" /> 886-7-7261010
          </span>
          <span class="flex items-center gap-2 hover:text-white transition-colors cursor-pointer">
            <Mail :size="12" /> juntai.wu01@gmail.com
          </span>
        </div>
        <div class="flex gap-4 tracking-widest uppercase">
          <span class="text-yellow-500 font-bold">EST. 1993</span>
          <span class="text-slate-600">|</span>
          <span class="hover:text-white transition-colors cursor-pointer">專業工業地坪工程</span>
        </div>
      </div>
    </div>

    <!-- Header -->
    <header class="sticky top-0 z-50 bg-white border-b border-slate-200">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-[72px]">
          <!-- Logo -->
          <NuxtLink to="/" class="flex-shrink-0 flex items-center gap-3 group">
            <div class="border border-slate-200 p-0.5 rounded-sm bg-slate-50">
              <img src="~/assets/logo.jpg" alt="俊泰工程 Logo" class="w-9 h-9 rounded-none object-cover group-hover:opacity-90 transition-opacity" />
            </div>
            <div>
              <h1 class="text-lg font-extrabold text-slate-900 tracking-tight leading-tight group-hover:text-yellow-600 transition-colors">俊泰工程</h1>
              <p class="text-[9px] text-slate-500 font-mono tracking-widest uppercase leading-tight font-bold">Juntai Eng.</p>
            </div>
          </NuxtLink>

          <!-- Desktop Navigation -->
          <nav class="hidden md:flex space-x-1">
            <NuxtLink
              v-for="item in menuItems"
              :key="item.name"
              :to="item.path"
              class="text-[13px] font-bold transition-all relative px-4 py-2 hover:bg-slate-50 border border-transparent rounded-sm flex items-center gap-1.5"
              :class="route.path === item.path ? 'text-yellow-600 border-b-yellow-600 bg-yellow-50/50' : 'text-slate-600 hover:text-slate-900'"
            >
              <component :is="item.icon" class="w-4 h-4 opacity-70" />
              {{ item.name }}
            </NuxtLink>
          </nav>
          
          <div class="hidden md:flex items-center border-l border-slate-200 pl-6 ml-2">
            <NuxtLink to="/contact" class="bg-slate-900 text-white hover:bg-yellow-600 text-xs font-bold px-4 py-2 transition-colors uppercase tracking-wider rounded-sm flex items-center gap-2">
              取得報價 <ArrowRight :size="14" />
            </NuxtLink>
          </div>

          <!-- Mobile Menu Button -->
          <div class="md:hidden">
            <button
              @click="isMenuOpen = !isMenuOpen"
              class="p-2 text-slate-600 hover:text-slate-900 hover:bg-slate-100 focus:outline-none rounded-sm"
            >
              <X v-if="isMenuOpen" :size="24" />
              <Menu v-else :size="24" />
            </button>
          </div>
        </div>
      </div>

      <!-- Mobile Menu -->
      <transition
        enter-active-class="transition duration-200 ease-out"
        enter-from-class="opacity-0 -translate-y-2"
        enter-to-class="opacity-100 translate-y-0"
        leave-active-class="transition duration-150 ease-in"
        leave-from-class="opacity-100 translate-y-0"
        leave-to-class="opacity-0 -translate-y-2"
      >
        <div v-if="isMenuOpen" class="md:hidden bg-white border-b border-slate-200 overflow-hidden absolute w-full shadow-lg">
          <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3 bg-white border-b border-slate-200 shadow-xl relative z-50">
            <NuxtLink
              v-for="item in menuItems"
              :key="item.name"
              :to="item.path"
              @click="isMenuOpen = false"
              class="px-3 py-3 text-sm font-bold border-b border-slate-100 last:border-0 rounded-sm flex items-center gap-2"
              :class="route.path === item.path ? 'text-yellow-600 bg-yellow-50 border-l-2 border-l-yellow-600' : 'text-slate-700 hover:text-yellow-600 hover:bg-slate-50'"
            >
              <component :is="item.icon" class="w-4 h-4 opacity-70" />
              {{ item.name }}
            </NuxtLink>
            <NuxtLink
              to="/contact"
              @click="isMenuOpen = false"
              class="flex items-center justify-center gap-2 w-full text-center bg-slate-900 text-white font-bold py-3 text-sm uppercase tracking-widest mt-4 rounded-sm"
            >
              取得工程報價 <ArrowRight :size="16" />
            </NuxtLink>
          </div>
        </div>
      </transition>
    </header>

    <!-- Main Content -->
    <main>
      <slot />
    </main>

    <!-- Footer -->
    <footer class="bg-slate-950 text-slate-400 py-16 border-t-[8px] border-yellow-600">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 md:grid-cols-4 gap-12 lg:gap-16">
          <div class="col-span-1 md:col-span-2">
            <NuxtLink to="/" class="flex flex-col mb-6 group w-fit">
              <div class="flex items-center gap-3">
                <div class="border border-slate-800 p-0.5 rounded-sm bg-slate-900">
                  <img src="~/assets/logo.jpg" alt="俊泰工程 Logo" class="w-8 h-8 rounded-none object-cover group-hover:opacity-90 transition-opacity" />
                </div>
                <span class="text-xl font-extrabold text-white group-hover:text-yellow-400 transition-colors tracking-tight">俊泰工程有限公司</span>
              </div>
              <p class="text-[10px] text-slate-500 font-mono tracking-widest uppercase mt-1">Juntai Engineering Co., Ltd.</p>
            </NuxtLink>
            <p class="text-sm leading-relaxed max-w-md mb-8 text-slate-500 font-light">
              成立於民國八十二年。專責規劃與施工工業級高強度地坪，具備豐富大型指標性廠房與公共工程實績，是您最值得信賴的工程夥伴。
            </p>
            <div class="flex gap-3">
              <a href="#" class="w-10 h-10 border border-slate-800 rounded-sm bg-slate-900 flex items-center justify-center hover:bg-yellow-600 hover:border-yellow-600 hover:text-white transition-colors cursor-pointer">
                <Facebook :size="18" />
              </a>
              <a href="#" class="w-10 h-10 border border-slate-800 rounded-sm bg-slate-900 flex items-center justify-center hover:bg-yellow-600 hover:border-yellow-600 hover:text-white transition-colors cursor-pointer">
                <Linkedin :size="18" />
              </a>
            </div>
          </div>
          
          <div>
            <h3 class="text-white font-bold mb-6 text-sm uppercase tracking-wider font-mono">Core Services</h3>
            <ul class="space-y-4 text-sm font-medium">
              <li><NuxtLink to="/epoxy" class="hover:text-yellow-400 transition-colors flex items-center gap-2 decoration-slate-700 hover:underline"><Code :size="12" class="text-yellow-500"/> 什麼是 EPOXY？</NuxtLink></li>
              <li><NuxtLink to="/services/1" class="hover:text-yellow-400 transition-colors flex items-center gap-2 decoration-slate-700 hover:underline"><Code :size="12" class="text-yellow-500"/> EPOXY 無塵地板</NuxtLink></li>
              <li><NuxtLink to="/services/2" class="hover:text-yellow-400 transition-colors flex items-center gap-2 decoration-slate-700 hover:underline"><Code :size="12" class="text-yellow-500"/> 導電環氧樹脂系統</NuxtLink></li>
              <li><NuxtLink to="/services/3" class="hover:text-yellow-400 transition-colors flex items-center gap-2 decoration-slate-700 hover:underline"><Code :size="12" class="text-yellow-500"/> 耐酸鹼 FRP 防護</NuxtLink></li>
              <li><NuxtLink to="/services/6" class="hover:text-yellow-400 transition-colors flex items-center gap-2 decoration-slate-700 hover:underline"><Code :size="12" class="text-yellow-500"/> U-MORTAR 高強度地坪</NuxtLink></li>
            </ul>
          </div>

          <div>
            <h3 class="text-white font-bold mb-6 text-sm uppercase tracking-wider font-mono">Contact Info</h3>
            <ul class="space-y-5 text-sm">
              <li class="flex items-start gap-4">
                <MapPin :size="18" class="text-yellow-500 shrink-0 mt-0.5" />
                <span class="leading-relaxed">高雄市前鎮區<br/>瑞祥街142號</span>
              </li>
              <li class="flex items-center gap-4">
                <Phone :size="18" class="text-yellow-500 shrink-0" />
                <span class="font-mono">886-7-7261010</span>
              </li>
              <li class="flex items-center gap-4">
                <Mail :size="18" class="text-yellow-500 shrink-0" />
                <a href="mailto:juntai.wu01@gmail.com" class="hover:text-yellow-400 transition-colors">juntai.wu01@gmail.com</a>
              </li>
            </ul>
          </div>
        </div>
        <div class="border-t border-slate-900 mt-16 pt-8 flex flex-col md:flex-row justify-between items-center text-[11px] font-mono text-slate-600">
          <p>COPYRIGHT &copy; 2026 JUNTAI ENGINEERING CO., LTD. ALL RIGHTS RESERVED.</p>
          <div class="flex gap-6 mt-4 md:mt-0 font-sans text-xs">
            <NuxtLink to="/privacy" class="hover:text-slate-400 transition-colors">隱私權政策</NuxtLink>
            <NuxtLink to="/terms" class="hover:text-slate-400 transition-colors">服務條款</NuxtLink>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>
