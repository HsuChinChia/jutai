<script setup lang="ts">
import { 
  ArrowRight, 
  Layers, 
  Zap, 
  Shield, 
  Droplets, 
  Sparkles, 
  Hammer, 
  CheckSquare 
} from 'lucide-vue-next'

const services = [
  {
    id: 1,
    title: 'EPOXY 無塵地板',
    description: '專為高度潔淨環境設計。表面平整無縫，耐磨損易清潔，適用於電子廠、食品廠及醫療空間。',
    icon: Layers,
    features: ['無縫一體成型', '不起塵易清潔', '耐磨耗抗衝擊']
  },
  {
    id: 2,
    title: '導電/抗靜電地坪',
    description: '有效消除靜電累積，保護精密電子設備。符合國際 ESD 標準，高科技產業的首選防護。',
    icon: Zap,
    features: ['穩定導電值', '防止靜電火花', '符合國際標準']
  },
  {
    id: 3,
    title: '耐酸鹼 FRP 地板',
    description: '玻璃纖維強化塑膠積層工法，具備極佳耐化學腐蝕特性，專攻化學槽與高腐蝕環境。',
    icon: Shield,
    features: ['優異耐酸鹼', '高機械強度', '完全防水防漏']
  },
  {
    id: 4,
    title: 'PU 防水工程',
    description: '針對廠房頂樓、外牆的專業防水處理。高彈性延展特性，有效抵抗建築物熱脹冷縮。',
    icon: Droplets,
    features: ['高彈性抗裂', '耐候抗紫外線', '隔絕水氣滲透']
  },
  {
    id: 5,
    title: '外牆防汙保護系統',
    description: '為建築外層提供透明工程保護膜，防止重工業汙垢附著，兼具優異的防水與透氣機能。',
    icon: Sparkles,
    features: ['防汙強自潔', '微孔結構透氣', '抗UV不黃變']
  },
  {
    id: 6,
    title: 'U-MORTAR 高強度地坪',
    description: '專為重載機具區設計的粗獷樹脂砂漿地坪，極高抗壓強度，適合堆高機頻繁輾壓的倉儲區。',
    icon: Hammer,
    features: ['超高抗壓強度', '耐重壓耐磨損', '重工業級止滑']
  }
]

const workflows = [
  { step: '01', title: '現場勘估', desc: '專業技師實地丈量與濕度/基面檢測。' },
  { step: '02', title: '圖面/材料規劃', desc: '選定最符合業界規範的工業級塗料與工法。' },
  { step: '03', title: '素地研磨', desc: '採用重裝鑽石研磨機具進行基底刨除整平。' },
  { step: '04', title: '多層次施工', desc: '底中面漆嚴謹工序，無縫鏝塗硬化成型。' },
  { step: '05', title: '品質測實驗收', desc: '厚度、平整度與導電測試達標後正式交付。' }
]
</script>

<template>
  <NuxtLayout>
    <!-- Hero Section -->
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
            <div class="h-1 w-12 bg-yellow-600" />
            <span class="text-yellow-500 font-mono uppercase tracking-[0.2em] text-sm font-bold">Solutions</span>
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

    <!-- Services Grid -->
    <section class="py-24 bg-slate-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          
          <div 
            v-for="(service, index) in services" 
            :key="index"
            class="bg-white p-10 lg:p-12 border border-slate-200 rounded-sm shadow-sm hover:shadow-xl hover:border-slate-300 transition-all duration-300 group flex flex-col h-full relative overflow-hidden"
          >
            <!-- Decorative Blueprint Corners -->
            <div class="absolute top-0 right-0 w-12 h-12 bg-[linear-gradient(45deg,transparent_49%,#e2e8f0_50%,transparent_51%)] bg-[size:8px_8px] opacity-0 group-hover:opacity-100 transition-opacity" />

            <!-- Hexagon Icon -->
            <div class="mb-8 inline-flex items-center justify-center w-16 h-16 bg-slate-100 border border-slate-200 text-slate-700 group-hover:bg-yellow-600 group-hover:border-yellow-600 group-hover:text-white transition-colors duration-300 relative z-10" style="clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);">
              <component :is="service.icon" class="w-7 h-7" />
            </div>

            <h3 class="text-xl font-extrabold text-slate-900 mb-4 tracking-tight group-hover:text-yellow-600 transition-colors relative z-10">
              {{ service.title }}
            </h3>
            
            <p class="text-slate-600 text-[13px] leading-relaxed mb-8 flex-1 relative z-10">
              {{ service.description }}
            </p>

            <ul class="space-y-3 mb-10 relative z-10">
              <li v-for="feat in service.features" :key="feat" class="flex items-center gap-3 text-[13px] text-slate-600 font-bold">
                <div class="w-1.5 h-1.5 bg-yellow-600 rounded-sm shadow-sm" /> {{ feat }}
              </li>
            </ul>

            <NuxtLink :to="`/services/${service.id}`" class="mt-auto inline-flex items-center gap-2 text-[12px] font-bold text-yellow-600 tracking-widest uppercase hover:text-yellow-800 transition-colors relative z-10">
              詳細規格 <ArrowRight class="w-4 h-4 group-hover:translate-x-1 transition-transform" />
            </NuxtLink>
          </div>

        </div>
      </div>
    </section>

    <!-- Workflow Section -->
    <section class="py-24 bg-slate-950 text-center relative overflow-hidden">
      <!-- Stronger Grid Background -->
      <div class="absolute inset-0 bg-[linear-gradient(to_right,#1e293b80_1px,transparent_1px),linear-gradient(to_bottom,#1e293b80_1px,transparent_1px)] bg-[size:32px_32px]" />

      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
        <div class="mb-16">
          <div class="text-yellow-500 font-mono tracking-[0.2em] text-[10px] font-bold uppercase mb-4">Standard Workflow</div>
          <h2 class="text-3xl font-extrabold text-white tracking-tight">嚴謹的標準化施工作業</h2>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-5 gap-6">
          <div 
            v-for="flow in workflows" 
            :key="flow.step"
            class="group bg-slate-900 border border-transparent hover:border-yellow-600/50 p-8 transition-all duration-300 relative flex flex-col items-center"
          >
            <!-- Highlight Box connected to border -->
            <div class="inline-flex w-[70px] h-[70px] items-center justify-center border border-slate-700 bg-transparent group-hover:bg-yellow-600 group-hover:border-yellow-500 font-mono text-xl text-white font-bold mb-8 transition-colors duration-300 absolute -top-8 left-1/2 -translate-x-1/2">
              {{ flow.step }}
            </div>
            
            <div class="pt-6 w-full mt-4">
              <h4 class="text-white font-bold mb-4 text-sm whitespace-nowrap overflow-hidden text-ellipsis">{{ flow.title }}</h4>
              <p class="text-slate-400 text-[12px] leading-relaxed font-light text-center">
                {{ flow.desc }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Bottom CTA -->
    <section class="py-24  relative border-t-4 border-yellow-600">
      <div class="absolute inset-0  bg-[size:40px_40px]" />
      <div class="relative z-10 max-w-4xl mx-auto px-4 text-center">
        <h2 class="text-3xl font-extrabold  mb-6 tracking-tight">需要專業的地坪工程建議嗎？</h2>
        <p class="text-slate-400 text-sm max-w-2xl mx-auto leading-relaxed mb-10">
          我們的工程團隊隨時準備為您提供免費的勘查評估，精準計算用料與排程，提供最具經濟效益的工業解決方案。
        </p>
        <NuxtLink 
          to="/contact" 
          class="inline-flex items-center justify-center gap-2 bg-blue-600 text-white px-8 py-3.5 text-sm font-bold tracking-wider hover:bg-slate-800 border border-transparent hover:border-blue-600 hover:text-blue-400 transition-colors rounded-sm shadow-lg shadow-blue-600/20"
        >
          聯絡工程部 <ArrowRight class="w-4 h-4" />
        </NuxtLink>
      </div>
    </section>

  </NuxtLayout>
</template>

<style scoped>
/* Optional: any specific scoped animations if needed */
</style>
