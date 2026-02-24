<script setup lang="ts">
import { ref, computed } from 'vue'
import { Filter, ArrowRight, MapPin, Calendar, CheckSquare } from 'lucide-vue-next'

const activeFilter = ref('all')

const projects = [
  {
    id: 1,
    title: '新竹科學園區半導體廠',
    category: 'electronics',
    location: '新竹市',
    date: '2025.10',
    image: 'https://images.unsplash.com/photo-1581091226825-a6a2a5aee158?q=80&w=800&auto=format&fit=crop',
    description: 'Class 100 無塵室導電地坪施工，面積 2,500 坪。採用高規格抗靜電 EPOXY 系統，確保精密製程環境安全。'
  },
  {
    id: 2,
    title: '桃園大型食品加工廠',
    category: 'food',
    location: '桃園市',
    date: '2025.08',
    image: 'https://images.unsplash.com/photo-1587293852726-70cdb56c2866?q=80&w=800&auto=format&fit=crop',
    description: 'HACCP 標準食品級地坪，具備耐熱水沖洗、抗油汙、防滑特性。針對濕式作業區加強止滑處理。'
  },
  {
    id: 3,
    title: '台中精密機械廠房',
    category: 'industrial',
    location: '台中市',
    date: '2025.05',
    image: 'https://images.unsplash.com/photo-1565106430482-8f6e74349ca1?q=80&w=800&auto=format&fit=crop',
    description: '重載作業區 U-MORTAR 高強度樹脂砂漿地坪，可承受堆高機頻繁重壓與金屬切削液侵蝕。'
  },
  {
    id: 4,
    title: '台北醫學中心實驗室',
    category: 'medical',
    location: '台北市',
    date: '2025.03',
    image: 'https://images.unsplash.com/photo-1582719508461-905c673771fd?q=80&w=800&auto=format&fit=crop',
    description: '抗化學腐蝕 FRP 地坪，針對實驗室酸鹼試劑操作區提供最高等級防護，並具備無縫易清潔特性。'
  },
  {
    id: 5,
    title: '高雄物流倉儲中心',
    category: 'industrial',
    location: '高雄市',
    date: '2024.12',
    image: 'https://images.unsplash.com/photo-1586528116311-ad8dd3c8310d?q=80&w=800&auto=format&fit=crop',
    description: '超耐磨 EPOXY 地坪，針對高流量物流通道進行強化，並規劃清晰的動線標示與安全警示區。'
  },
  {
    id: 6,
    title: '台南科技大樓地下停車場',
    category: 'commercial',
    location: '台南市',
    date: '2024.10',
    image: 'https://images.unsplash.com/photo-1506521781263-d8422e82f27a?q=80&w=800&auto=format&fit=crop',
    description: '止滑型 EPOXY 車道與耐磨車位地坪，色彩分區規劃，提升停車場明亮度與指引性。'
  }
]

const categories = [
  { id: 'all', name: '全部實績' },
  { id: 'electronics', name: '電子科技' },
  { id: 'food', name: '食品生技' },
  { id: 'industrial', name: '重工製造' },
  { id: 'medical', name: '醫療實驗' },
  { id: 'commercial', name: '商業倉儲' }
]

const filteredProjects = computed(() => {
  if (activeFilter.value === 'all') return projects
  return projects.filter(p => p.category === activeFilter.value)
})
</script>

<template>
  <NuxtLayout>
    <!-- Industrial Hero Section -->
    <section class="relative h-[40vh] min-h-[300px] flex items-center justify-center overflow-hidden bg-slate-900 border-b-2 border-slate-800">
      <div class="absolute inset-0 z-0">
        <img 
          src="https://images.unsplash.com/photo-1541888086425-d81bb19240f5?q=80&w=1920&auto=format&fit=crop" 
          alt="Project Gallery Background" 
          class="w-full h-full object-cover grayscale-[30%] opacity-40 mix-blend-overlay"
          referrerPolicy="no-referrer"
        />
      </div>
      <div class="absolute inset-0 bg-gradient-to-r from-slate-900 via-slate-900/80 to-transparent z-10" />
      
      <!-- Pattern Overlay -->
      <div class="absolute inset-0 bg-[radial-gradient(#ffffff0a_1px,transparent_1px)] [background-size:20px_20px] z-10 opacity-50" />
      
      <div class="relative z-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 w-full pt-10">
        <div class="max-w-3xl animate-fade-in-up">
          <div class="flex items-center gap-4 mb-4">
            <div class="h-1 w-12 bg-yellow-600" />
            <span class="text-yellow-500 font-mono uppercase tracking-[0.2em] text-sm font-bold">Portfolios</span>
          </div>
          <h1 class="text-4xl md:text-6xl font-extrabold text-white mb-6 tracking-tight">
            工程實績藍圖
          </h1>
          <p class="text-lg text-slate-400 font-light leading-relaxed border-l-2 border-slate-700 pl-4">
            見證我們在全台各大企業與公共建設中的專業施工成果，<br class="hidden sm:block"/>品質是我們唯一的妥協準則。
          </p>
        </div>
      </div>
    </section>

    <!-- Gallery Section -->
    <section class="py-24 bg-slate-50 min-h-screen">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        
        <!-- Filter Tabs -->
        <div class="flex flex-wrap justify-center gap-2 mb-16">
          <button 
            v-for="cat in categories" 
            :key="cat.id"
            @click="activeFilter = cat.id"
            class="px-6 py-2 rounded-sm text-sm font-bold tracking-wide uppercase transition-all duration-300 border focus:outline-none"
            :class="activeFilter === cat.id 
              ? 'bg-slate-900 text-white border-slate-900' 
              : 'bg-white text-slate-500 border-slate-200 hover:border-slate-400 hover:text-slate-900'"
          >
            {{ cat.name }}
          </button>
        </div>

        <!-- Projects Grid -->
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <TransitionGroup name="list">
            <div 
              v-for="project in filteredProjects" 
              :key="project.id"
              class="group bg-white rounded-sm overflow-hidden border border-slate-200 flex flex-col h-full hover:border-yellow-500 transition-colors shadow-sm"
            >
              <!-- Category Badge (Absolute) -->
              <div class="p-4 border-b border-slate-200 bg-white flex justify-between items-center z-10 transition-colors duration-300 group-hover:bg-slate-50">
                <span class="text-[11px] font-bold text-slate-900 uppercase tracking-widest flex items-center gap-2">
                   <div class="w-1.5 h-1.5 bg-yellow-600 rounded-full" />
                   {{ categories.find(c => c.id === project.category)?.name }}
                </span>
                <span class="text-[10px] text-slate-400 font-mono tracking-widest border border-slate-200 px-2 py-0.5 rounded-sm">
                  ID #{{ project.id.toString().padStart(3, '0') }}
                </span>
              </div>

              <!-- Image -->
              <div class="relative h-56 overflow-hidden border-b border-slate-200">
                <img 
                  :src="project.image" 
                  :alt="project.title" 
                  class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-[1.03] grayscale-[15%]"
                  referrerPolicy="no-referrer"
                />
                <div class="absolute inset-0 bg-gradient-to-t from-slate-900/60 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300" />
              </div>

              <!-- Content -->
              <div class="p-6 flex-1 flex flex-col bg-white">
                <div class="flex items-center gap-4 text-[11px] text-slate-500 mb-4 font-mono font-bold tracking-wider">
                  <span class="flex items-center gap-1.5">
                    <MapPin :size="12" class="text-yellow-500" /> {{ project.location }}
                  </span>
                  <span class="flex items-center gap-1.5 border-l border-slate-300 pl-4">
                    <Calendar :size="12" class="text-yellow-500" /> {{ project.date }}
                  </span>
                </div>

                <h3 class="text-xl font-extrabold text-slate-900 mb-4 tracking-tight group-hover:text-yellow-600 transition-colors">
                  {{ project.title }}
                </h3>
                
                <p class="text-slate-600 text-sm leading-relaxed mb-6 font-light flex-1">
                  {{ project.description }}
                </p>

                <div class="pt-4 border-t border-slate-100 mt-auto">
                  <button class="w-full py-3 bg-slate-50 text-slate-700 hover:bg-slate-900 hover:text-white transition-colors text-[12px] font-bold uppercase tracking-widest border border-transparent rounded-sm focus:outline-none focus:ring-2 focus:ring-yellow-600 focus:ring-offset-1 flex items-center justify-center gap-2">
                    詳細規格 <ArrowRight :size="14" />
                  </button>
                </div>
              </div>
            </div>
          </TransitionGroup>
        </div>

        <!-- Empty State -->
        <div v-if="filteredProjects.length === 0" class="text-center py-24 bg-white border border-slate-200 rounded-sm">
          <Filter :size="32" class="mx-auto mb-4 text-slate-300" />
          <p class="text-slate-500 font-mono text-sm tracking-wider uppercase">NO RECORDS FOUND IN THIS CATEGORY.</p>
        </div>

      </div>
    </section>

    <!-- Prompt CTA -->
    <section class="py-20 bg-slate-950 text-center border-t border-slate-800">
      <div class="max-w-3xl mx-auto px-4">
        <h2 class="text-2xl font-bold text-white mb-6">您的廠房也需要打造同樣標準的防護層嗎？</h2>
        <NuxtLink 
          to="/contact"
          class="inline-flex items-center gap-2 bg-yellow-600 text-white font-bold px-8 py-3 rounded-sm border border-transparent hover:bg-slate-900 hover:border-yellow-500 transition-colors uppercase tracking-wider text-sm"
        >
          與我們聯繫
        </NuxtLink>
      </div>
    </section>
  </NuxtLayout>
</template>

<style scoped>
.animate-fade-in-up {
  animation: fadeInUp 0.8s ease-out forwards;
  opacity: 0;
  transform: translateY(20px);
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* List Transitions */
.list-move,
.list-enter-active,
.list-leave-active {
  transition: all 0.4s ease;
}

.list-enter-from,
.list-leave-to {
  opacity: 0;
  transform: scale(0.98);
}

.list-leave-active {
  position: absolute;
}
</style>
