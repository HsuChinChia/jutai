<script setup lang="ts">
import { CheckCircle, Shield, Zap, Layers, Award, Users, ArrowRight } from 'lucide-vue-next'
</script>

<template>
  <NuxtLayout>
    <!-- Hero Section -->
    <section class="relative h-[60vh] min-h-[500px] flex items-center justify-center overflow-hidden bg-slate-900">
      <div class="absolute inset-0 z-0 opacity-40">
        <img 
          src="https://picsum.photos/seed/industrial/1920/1080?blur=2" 
          alt="Industrial Flooring" 
          class="w-full h-full object-cover"
          referrerPolicy="no-referrer"
        />
      </div>
      <div class="absolute inset-0 bg-gradient-to-b from-slate-900/80 via-slate-900/50 to-slate-900 z-10" />
      
      <div class="relative z-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <div class="animate-fade-in-up">
          <h1 class="text-5xl md:text-7xl font-bold text-white mb-6 tracking-tight">
            建立堅實基礎 <br />
            <span class="text-yellow-500">自民國82年起</span>
          </h1>
          <p class="text-xl text-slate-300 max-w-2xl mx-auto font-light leading-relaxed">
            專業 EPOXY 地坪解決方案，專為耐用性、精確性和高性能而設計。
          </p>
        </div>
      </div>
    </section>

    <!-- Company Profile -->
    <section class="py-24 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div class="animate-fade-in-right">
            <div class="flex items-center gap-4 mb-6">
              <div class="h-1 w-12 bg-yellow-600 rounded-full" />
              <span class="text-yellow-600 font-bold uppercase tracking-widest text-sm">關於俊泰</span>
            </div>
            <h2 class="text-4xl font-bold text-slate-900 mb-8 leading-tight">
              開創工業地坪 <br />
              卓越品質
            </h2>
            <div class="space-y-6 text-slate-600 leading-relaxed">
              <p>
                俊泰工程有限公司成立於民國八十二年，為專業規劃 EPOXY 施工廠商。
              </p>
              <p>
                鑑於日新月異、精益求精的市場，營建業界對工程高品質之追求更甚，在創立時即以前瞻性之觀點致力於各種建材介面接著材料開發及新式施作工法之應用。
              </p>
              <p>
                並有幸參與臺灣多項重大公共工程建設，深獲營造業界之好評。
              </p>
            </div>
            
            <div class="mt-10 grid grid-cols-2 gap-8">
              <div class="border-l-4 border-yellow-100 pl-6">
                <div class="text-4xl font-bold text-yellow-600 mb-1">30+</div>
                <div class="text-sm text-slate-500 font-medium uppercase tracking-wide">年專業經驗</div>
              </div>
              <div class="border-l-4 border-yellow-100 pl-6">
                <div class="text-4xl font-bold text-yellow-600 mb-1">100%</div>
                <div class="text-sm text-slate-500 font-medium uppercase tracking-wide">品質承諾</div>
              </div>
            </div>
          </div>

          <div class="relative animate-fade-in-scale">
            <div class="absolute -inset-4 bg-yellow-600/5 rounded-2xl transform rotate-3" />
            <img 
              src="https://picsum.photos/seed/construction/800/1000" 
              alt="Construction Site" 
              class="relative rounded-xl shadow-2xl w-full object-cover h-[600px]"
              referrerPolicy="no-referrer"
            />
            <div class="absolute bottom-8 left-8 right-8 bg-white/95 backdrop-blur p-6 rounded-lg shadow-lg border border-slate-100">
              <div class="flex items-start gap-4">
                <div class="bg-yellow-600 p-3 rounded-full text-white">
                  <Award :size="24" />
                </div>
                <div>
                  <h4 class="font-bold text-slate-900 mb-1">認證卓越</h4>
                  <p class="text-sm text-slate-600">在公共和私營部門項目中獲得卓越品質認可。</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Philosophy / Mission -->
    <section class="py-24 bg-slate-50 border-y border-slate-200">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center max-w-3xl mx-auto mb-16">
          <h2 class="text-3xl font-bold text-slate-900 mb-4">核心理念</h2>
          <p class="text-slate-600">
            期望能以更高品質產品與服務及經濟之價格供應市場，降低業界成本，並秉持一貫誠信經營、專業技術與熱誠服務之理念為社會大眾謀福。
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div 
            v-for="(item, index) in [
              {
                icon: Shield,
                title: '誠信經營',
                desc: '誠實運營和透明的商業實踐是我們與客戶建立信任的基礎。'
              },
              {
                icon: Zap,
                title: '專業技術',
                desc: '持續創新材料開發和應用方法，以滿足現代需求。'
              },
              {
                icon: Users,
                title: '熱誠服務',
                desc: '致力於通過積極和承諾的客戶服務造福大眾。'
              }
            ]" 
            :key="index"
            class="bg-white p-8 rounded-2xl shadow-sm hover:shadow-md transition-shadow border border-slate-100 animate-fade-in-up"
            :style="{ animationDelay: `${index * 200}ms` }"
          >
            <div class="w-14 h-14 bg-yellow-50 rounded-xl flex items-center justify-center mb-6">
              <component :is="item.icon" class="w-8 h-8 text-yellow-600" />
            </div>
            <h3 class="text-xl font-bold text-slate-900 mb-3">{{ item.title }}</h3>
            <p class="text-slate-600 leading-relaxed text-sm">
              {{ item.desc }}
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Grid -->
    <section class="py-24 bg-slate-900 text-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex flex-col md:flex-row justify-between items-end mb-16 gap-6">
          <div>
            <div class="flex items-center gap-4 mb-4">
              <div class="h-1 w-12 bg-yellow-500 rounded-full" />
              <span class="text-yellow-400 font-bold uppercase tracking-widest text-sm">服務項目</span>
            </div>
            <h2 class="text-4xl font-bold text-white">全方位解決方案</h2>
          </div>
          <button class="flex items-center gap-2 text-white border border-white/20 px-6 py-3 rounded-full hover:bg-white hover:text-slate-900 transition-all group">
            查看所有服務 <ArrowRight :size="16" class="group-hover:translate-x-1 transition-transform" />
          </button>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-px bg-slate-800 border border-slate-800">
          <div 
            v-for="(service, index) in [
              'EPOXY 無塵地板',
              '導電環氧樹脂',
              '耐酸鹼 FRP 地板',
              'PU 防水工程',
              '外牆景觀防汙保護',
              '紫光瞬固地坪',
              'U MORTAR 地坪工程',
              '建材介面接著劑開發',
              '無縫止滑地坪'
            ]" 
            :key="index"
            class="bg-slate-900 p-10 hover:bg-slate-800 transition-colors group cursor-pointer"
          >
            <div class="flex justify-between items-start mb-8">
              <Layers class="text-slate-600 group-hover:text-yellow-400 transition-colors" :size="32" />
              <span class="text-slate-700 font-mono text-sm">0{{ index + 1 }}</span>
            </div>
            <h3 class="text-xl font-bold text-slate-200 group-hover:text-white mb-2">{{ service }}</h3>
            <p class="text-slate-500 text-sm leading-relaxed mb-6">
              適用於工業和商業環境的高性能應用。
            </p>
            <div class="flex items-center gap-2 text-yellow-500 text-sm font-medium opacity-0 group-hover:opacity-100 transition-opacity transform translate-y-2 group-hover:translate-y-0">
              了解更多 <ArrowRight :size="14" />
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Applications -->
    <section class="py-24 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16">
          <div>
            <h2 class="text-3xl font-bold text-slate-900 mb-8">適用場所</h2>
            <p class="text-slate-600 mb-8">
              我們的 EPOXY 和 FRP 解決方案專為需要嚴格衛生、耐用和安全標準的環境而設計。
            </p>
            <ul class="space-y-4">
              <li 
                v-for="(item, index) in [
                  '高科技廠房',
                  '藥廠',
                  '食品廠',
                  '無塵作業區',
                  '商業停車場',
                  '醫院與實驗室',
                  '倉庫與物流中心'
                ]" 
                :key="index"
                class="flex items-center gap-3 text-slate-700"
              >
                <CheckCircle :size="20" class="text-yellow-500 flex-shrink-0" />
                <span>{{ item }}</span>
              </li>
            </ul>
          </div>
          <div class="grid grid-cols-2 gap-4">
            <img 
              src="https://picsum.photos/seed/factory/400/500" 
              alt="Factory Floor" 
              class="rounded-2xl object-cover h-full w-full"
              referrerPolicy="no-referrer"
            />
            <div class="space-y-4">
              <img 
                src="https://picsum.photos/seed/lab/400/240" 
                alt="Lab Floor" 
                class="rounded-2xl object-cover h-48 w-full"
                referrerPolicy="no-referrer"
              />
              <div class="bg-slate-100 rounded-2xl p-6 h-auto flex flex-col justify-center">
                <div class="text-4xl font-bold text-slate-900 mb-2">100%</div>
                <div class="text-sm text-slate-500">符合無塵標準</div>
              </div>
            </div>
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

.animate-fade-in-right {
  animation: fadeInRight 0.8s ease-out forwards;
  opacity: 0;
  transform: translateX(-20px);
}

.animate-fade-in-scale {
  animation: fadeInScale 0.8s ease-out forwards;
  opacity: 0;
  transform: scale(0.9);
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInRight {
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeInScale {
  to {
    opacity: 1;
    transform: scale(1);
  }
}
</style>
