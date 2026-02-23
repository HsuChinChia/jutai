<script setup lang="ts">
import { ArrowRight, Drill, ShieldAlert, Sparkles, Building2, Beaker, HardHat, CheckSquare, Layers } from 'lucide-vue-next'

const services = [
  {
    id: 1,
    title: 'EPOXY 無塵地坪',
    description: '適用於高科技無塵室、生技藥廠與精密電子廠。具備極佳的耐磨耗性、不起塵、易清潔，且能有效防堵靜電破壞。',
    icon: Sparkles,
    specs: ['Class 100~100K', '抗靜電 10^4~10^6 Ω', '耐重壓 500kg/cm²'],
    features: ['無縫平滑表面', '高分子接著抗剝離', '抗微汙染析出']
  },
  {
    id: 2,
    title: '耐酸鹼 FRP 地坪防護',
    description: '專為高腐蝕性環境設計，如化學工廠、電鍍廠、實驗室等。強韌玻璃纖維層能有效阻絕強酸鹼侵蝕混凝土地基。',
    icon: Beaker,
    specs: ['高耐腐蝕等級', '抗熱衝擊防裂', '防漏止水處理'],
    features: ['三層 FRP 結構補強', '耐 98% 硫酸侵蝕', '乙烯基高抗切變']
  },
  {
    id: 3,
    title: '重載 U-MORTAR 砂漿',
    description: '針對堆高機頻繁輾壓、重型機械作業區設計。高強度環氧樹脂砂漿提供極高的抗衝擊性與耐磨損壽命。',
    icon: Building2,
    specs: ['重載荷抗壓', '耐磨耗率極低', '高平整度控制'],
    features: ['厚度 3mm~10mm', '抗金屬切削液', '吸收震動防裂']
  },
  {
    id: 4,
    title: 'PU 頂樓防水工程',
    description: '提供極佳的伸長率與耐候性。適用於商業大樓頂樓、露台、中庭等防水工程，能有效適應建築物的熱脹冷縮。',
    icon: Layers,
    specs: ['超強抗拉伸率', '優異耐候抗 UV', '無縫防水層'],
    features: ['彈性體防水材', '底中面三道漆膜', '壽命長達 10 年']
  },
  {
    id: 5,
    title: '止滑車道地坪',
    description: '專為地下停車場、物流轉運站、車道坡道設計。提供優異的輪胎抓地力，減少打滑風險，並能規劃動線標線。',
    icon: HardHat,
    specs: ['矽砂止滑係數高', '輪胎摩擦無異音', '色彩分區警示'],
    features: ['降低行車噪音', '抗油汙易清洗', '耐車輛頻繁輾壓']
  },
  {
    id: 6,
    title: '建築外牆防汙保護',
    description: '採用特殊防護塗層，能有效對抗酸雨侵蝕與空氣汙染物附著。使建築外觀長保如新，降低後續清潔維護成本。',
    icon: ShieldAlert,
    specs: ['奈米級防汙抗垢', '極佳耐候抗黃變', '高透氣不鼓起'],
    features: ['自潔效應', '防護漆膜壽命長', '保護底材免於風化']
  }
]
</script>

<template>
  <NuxtLayout>
    <!-- Industrial Hero Section -->
    <section class="relative h-[40vh] min-h-[300px] flex items-center justify-center overflow-hidden bg-slate-900 border-b-2 border-slate-800">
      <div class="absolute inset-0 z-0">
        <img 
          src="https://images.unsplash.com/photo-1541888086425-d81bb19240f5?q=80&w=1920&auto=format&fit=crop" 
          alt="Services Background" 
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
            <div class="h-1 w-12 bg-blue-600" />
            <span class="text-blue-500 font-mono uppercase tracking-[0.2em] text-sm font-bold">Solutions</span>
          </div>
          <h1 class="text-4xl md:text-6xl font-extrabold text-white mb-6 tracking-tight">
            全方位解決方案
          </h1>
          <p class="text-lg text-slate-400 font-light leading-relaxed border-l-2 border-slate-700 pl-4">
            適用於工業和商業環境的高性能應用，<br class="hidden sm:block"/>滿足最嚴苛的防護規範與安全標準。
          </p>
        </div>
      </div>
    </section>

    <!-- Services Grid Blueprint Style -->
    <section class="py-24 bg-slate-50 min-h-screen">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-0 border border-slate-200 bg-white shadow-sm">
          <div 
            v-for="(service, index) in services" 
            :key="service.id"
            class="group p-8 border-b md:border-b-0 lg:border-b lg:[&:nth-last-child(-n+3)]:border-b-0 border-slate-200 hover:bg-slate-50 transition-colors duration-300 relative overflow-hidden flex flex-col"
            :class="{'md:border-r': (index + 1) % 2 !== 0, 'lg:border-r': (index + 1) % 3 !== 0}"
          >
            <!-- Decorative Blueprint Corners -->
            <div class="absolute top-0 right-0 w-12 h-12 bg-[linear-gradient(45deg,transparent_49%,#e2e8f0_50%,transparent_51%)] bg-[size:8px_8px] opacity-0 group-hover:opacity-100 transition-opacity" />
            
            <div class="flex justify-between items-start mb-8 z-10 relative">
              <div class="w-14 h-14 bg-slate-100 flex items-center justify-center rounded-sm border border-slate-200 group-hover:bg-blue-600 group-hover:border-blue-600 transition-colors duration-300">
                <component :is="service.icon" class="w-7 h-7 text-slate-700 group-hover:text-white transition-colors" />
              </div>
              <span class="text-slate-400 font-mono text-[10px] font-bold tracking-widest border border-slate-200 px-2 py-1 rounded-sm bg-white">ID: 0{{ index + 1 }}</span>
            </div>
            
            <h3 class="text-2xl font-extrabold text-slate-900 mb-4 tracking-tight group-hover:text-blue-600 transition-colors z-10 relative">
              {{ service.title }}
            </h3>
            
            <p class="text-slate-600 text-sm leading-relaxed mb-6 font-light z-10 relative flex-1">
              {{ service.description }}
            </p>
            
            <div class="mt-auto space-y-4 pt-6 border-t border-slate-100 z-10 relative">
              <div>
                <strong class="text-[10px] uppercase tracking-widest text-slate-400 font-mono mb-2 block">Technical Specs_</strong>
                <ul class="space-y-1">
                  <li v-for="spec in service.specs" :key="spec" class="text-xs font-bold text-slate-700 flex items-center gap-2">
                    <div class="w-1 h-1 bg-blue-600 rounded-full" /> {{ spec }}
                  </li>
                </ul>
              </div>
            </div>
            
            <button class="mt-8 w-full py-3 bg-white text-slate-700 hover:bg-slate-900 hover:text-white transition-colors text-[12px] font-bold uppercase tracking-widest border border-slate-200 hover:border-slate-900 rounded-sm focus:outline-none flex items-center justify-center gap-2 z-10 relative">
              詳細規格 <ArrowRight :size="14" />
            </button>
          </div>
        </div>
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
</style>
