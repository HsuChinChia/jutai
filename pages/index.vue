<script setup lang="ts">
import { ArrowRight, Drill, ShieldAlert, Sparkles, Building2, Beaker, HardHat } from 'lucide-vue-next'
</script>

<template>
  <NuxtLayout>
    <!-- Hero Section -->
    <section class="relative h-screen flex items-center justify-center overflow-hidden bg-slate-900">
      <div class="absolute inset-0 z-0 opacity-30">
        <img 
          src="https://picsum.photos/seed/epoxy/1920/1080?blur=4" 
          alt="Epoxy Flooring Background" 
          class="w-full h-full object-cover"
          referrerPolicy="no-referrer"
        />
        <!-- Diagonal cut effect -->
        <div class="hidden md:block absolute inset-0 bg-slate-900" style="clip-path: polygon(0 0, 15% 0, 0 100%);" />
      </div>

      <div class="relative z-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 w-full py-20 mt-10 md:mt-0">
        <div class="max-w-3xl animate-fade-in-up">
          <div class="flex items-center gap-4 mb-6">
            <div class="h-1 w-12 bg-blue-600" />
            <span class="text-blue-500 font-mono uppercase tracking-[0.2em] text-sm font-bold">Industrial Grade Flooring</span>
          </div>
          <h1 class="text-5xl md:text-7xl font-extrabold text-white mb-8 leading-[1.1] tracking-tight">
            堅實基礎 <br />
            <span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-400 to-blue-200">專業鑄造</span>
          </h1>
          <p class="text-xl text-slate-400 mb-10 max-w-xl font-light leading-relaxed border-l-2 border-slate-700 pl-6">
            自民國82年起，俊泰工程提供最高標準的 EPOXY 及 FRP 地坪系統，滿足工業重載與高科技無塵環境的嚴苛要求。
          </p>
          <div class="flex flex-col sm:flex-row gap-4">
            <NuxtLink 
              to="/about" 
              class="bg-blue-600 hover:bg-blue-700 text-white px-8 py-4 font-bold transition-colors flex items-center justify-center gap-3 group rounded-sm shadow-lg shadow-blue-900/20"
            >
              了解工程實力 <ArrowRight :size="18" class="group-hover:translate-x-1 transition-transform" />
            </NuxtLink>
            <NuxtLink to="/projects" class="bg-slate-800 hover:bg-slate-700 border border-slate-700 hover:border-slate-500 text-white px-8 py-4 font-bold transition-colors flex items-center justify-center rounded-sm">
              查看實績藍圖
            </NuxtLink>
          </div>
          
          <!-- Quick Stats -->
          <div class="grid grid-cols-3 gap-4 sm:gap-8 mt-16 pt-8 border-t border-slate-800">
            <div>
              <div class="text-3xl font-bold text-white mb-1">30<span class="text-blue-500">+</span></div>
              <div class="text-xs text-slate-500 font-mono uppercase tracking-wider">Years Exp.</div>
            </div>
            <div>
              <div class="text-3xl font-bold text-white mb-1">100<span class="text-blue-500">%</span></div>
              <div class="text-xs text-slate-500 font-mono uppercase tracking-wider">Quality Rate</div>
            </div>
            <div>
              <div class="text-3xl font-bold text-white mb-1">99<span class="text-blue-500">%</span></div>
              <div class="text-xs text-slate-500 font-mono uppercase tracking-wider">On-time Build</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Core Engineering Standards Section -->
    <section class="py-24 bg-slate-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex flex-col md:flex-row justify-between items-end mb-16 gap-6">
          <div>
            <div class="flex items-center gap-4 mb-4">
              <span class="text-slate-500 font-mono uppercase tracking-[0.1em] text-sm font-bold">Core Capabilities</span>
            </div>
            <h2 class="text-4xl font-extrabold text-slate-900 tracking-tight">工程核心優勢</h2>
          </div>
        </div>

        <!-- Blueprint style grid -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-0 border border-slate-200 bg-white shadow-sm">
          <div class="p-10 border-b md:border-b-0 md:border-r border-slate-200 hover:bg-slate-50 transition-colors group cursor-pointer relative overflow-hidden">
            <div class="absolute top-0 right-0 w-16 h-16 bg-[linear-gradient(45deg,transparent_49%,#e2e8f0_50%,transparent_51%)] bg-[size:8px_8px] opacity-0 group-hover:opacity-100 transition-opacity" />
            <div class="w-12 h-12 bg-slate-100 flex items-center justify-center mb-6 rounded-sm group-hover:bg-blue-600 transition-colors">
              <Building2 class="w-6 h-6 text-slate-700 group-hover:text-white transition-colors" />
            </div>
            <h3 class="text-xl font-bold text-slate-900 mb-4 tracking-tight">重載耐磨防護</h3>
            <p class="text-slate-600 leading-relaxed text-sm">
              專為承受堆高機、重型機具頻繁輾壓設計。高強度環氧樹脂砂漿提供卓越的抗衝擊與耐磨耗性能，確保廠房地面長久如新。
            </p>
          </div>
          
          <div class="p-10 border-b md:border-b-0 md:border-r border-slate-200 hover:bg-slate-50 transition-colors group cursor-pointer relative overflow-hidden">
            <div class="absolute top-0 right-0 w-16 h-16 bg-[linear-gradient(45deg,transparent_49%,#e2e8f0_50%,transparent_51%)] bg-[size:8px_8px] opacity-0 group-hover:opacity-100 transition-opacity" />
            <div class="w-12 h-12 bg-slate-100 flex items-center justify-center mb-6 rounded-sm group-hover:bg-blue-600 transition-colors">
              <Beaker class="w-6 h-6 text-slate-700 group-hover:text-white transition-colors" />
            </div>
            <h3 class="text-xl font-bold text-slate-900 mb-4 tracking-tight">抗酸鹼化學防腐</h3>
            <p class="text-slate-600 leading-relaxed text-sm">
              採用頂級 FRP 玻璃纖維與乙烯基樹脂，為化工廠、實驗室等高腐蝕風險環境，提供滴水不漏的最高等級防護隔離層。
            </p>
          </div>

          <div class="p-10 hover:bg-slate-50 transition-colors group cursor-pointer relative overflow-hidden">
            <div class="absolute top-0 right-0 w-16 h-16 bg-[linear-gradient(45deg,transparent_49%,#e2e8f0_50%,transparent_51%)] bg-[size:8px_8px] opacity-0 group-hover:opacity-100 transition-opacity" />
            <div class="w-12 h-12 bg-slate-100 flex items-center justify-center mb-6 rounded-sm group-hover:bg-blue-600 transition-colors">
              <Sparkles class="w-6 h-6 text-slate-700 group-hover:text-white transition-colors" />
            </div>
            <h3 class="text-xl font-bold text-slate-900 mb-4 tracking-tight">無塵防靜電系統</h3>
            <p class="text-slate-600 leading-relaxed text-sm">
              符合最高無塵室規範。導電型地坪能穩定導散靜電，保護精密電子元件，為半導體與高科技製程把關環境安全。
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Tech Specs / Process -->
    <section class="py-24 bg-white border-t border-slate-200">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div>
            <h2 class="text-3xl font-extrabold text-slate-900 mb-6 tracking-tight">嚴謹的標準化施工流程</h2>
            <p class="text-slate-600 mb-8 leading-relaxed">
              地坪的壽命取決於基材的處理與施工細節。我們堅持多道工序，不容許任何妥協的品質控管，鑄造出如磐石般堅固的工程品質。
            </p>
            
            <div class="space-y-8">
              <div class="flex gap-6 items-start">
                <div class="font-mono font-bold text-slate-300 text-3xl mt-1 select-none">01</div>
                <div>
                  <h4 class="text-lg font-bold text-slate-900 mb-2">素地全面研磨與修補</h4>
                  <p class="text-sm text-slate-600 leading-relaxed">使用重型鑽石研磨機去除表面油汙與脆弱層，針對裂縫進行 V-cut 樹脂灌注補強，確保基地強度。</p>
                </div>
              </div>
              <div class="flex gap-6 items-start">
                <div class="font-mono font-bold text-slate-300 text-3xl mt-1 select-none">02</div>
                <div>
                  <h4 class="text-lg font-bold text-slate-900 mb-2">高滲透底漆接著</h4>
                  <p class="text-sm text-slate-600 leading-relaxed">塗佈專用滲透型底漆，深層封閉混凝土毛細孔，大幅提升面材與基底之間的分子級接著力。</p>
                </div>
              </div>
              <div class="flex gap-6 items-start">
                <div class="font-mono font-bold text-slate-300 text-3xl mt-1 select-none">03</div>
                <div>
                  <h4 class="text-lg font-bold text-slate-900 mb-2">無縫流展面塗層</h4>
                  <p class="text-sm text-slate-600 leading-relaxed">依承載需求進行抗壓中塗鏝平，最後完整覆蓋高硬度平滑面漆，達到一體無縫、易潔且具高抗性的完美表面。</p>
                </div>
              </div>
            </div>
          </div>
          
          <div class="relative">
            <!-- decorative elements -->
            <div class="hidden md:block absolute -top-4 -right-4 w-24 h-24 bg-[linear-gradient(to_right,#0000001a_1px,transparent_1px),linear-gradient(to_bottom,#0000001a_1px,transparent_1px)] bg-[size:8px_8px] z-0" />
            <div class="hidden md:block absolute -bottom-4 -left-4 w-24 h-24 bg-[linear-gradient(to_right,#0000001a_1px,transparent_1px),linear-gradient(to_bottom,#0000001a_1px,transparent_1px)] bg-[size:8px_8px] z-0" />
            
            <img 
              src="https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?q=80&w=800&auto=format&fit=crop" 
              alt="Engineering Precision" 
              class="relative z-10 w-full rounded-sm border border-slate-200 shadow-xl"
              referrerPolicy="no-referrer"
            />
            
            <!-- Quality Badge -->
            <div class="absolute -left-4 md:-left-8 top-12 bg-blue-600 text-white p-5 md:p-6 rounded-sm shadow-xl z-20 flex items-center gap-4 border border-blue-500">
              <HardHat :size="32" class="opacity-90" />
              <div>
                <div class="text-[10px] md:text-sm text-blue-200 font-mono tracking-wider">CERTIFIED</div>
                <div class="font-bold text-sm md:text-base">專業證照技師施工</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Call to Action -->
    <section class="py-24 bg-slate-900 relative overflow-hidden border-t-4 border-blue-600">
      <div class="absolute inset-0 bg-[linear-gradient(to_right,#ffffff0a_1px,transparent_1px),linear-gradient(to_bottom,#ffffff0a_1px,transparent_1px)] bg-[size:40px_40px]" />
      <div class="relative z-10 max-w-5xl mx-auto px-4 text-center">
        <h2 class="text-3xl md:text-5xl font-extrabold text-white mb-6 tracking-tight">準備好升級您的廠房地坪了嗎？</h2>
        <p class="text-slate-400 text-lg mb-10 max-w-2xl mx-auto font-light leading-relaxed">
          我們的工程團隊將提供最專業的現場勘估與報價，為您量身打造最符合製程規範的地坪解決方案。
        </p>
        <NuxtLink 
          to="/contact" 
          class="inline-flex bg-blue-600 text-white px-8 py-4 font-bold rounded-sm border border-transparent hover:bg-slate-900 hover:border-blue-600 hover:text-blue-400 transition-colors"
        >
          立即預約現場測量
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
</style>
