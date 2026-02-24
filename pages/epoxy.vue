<script setup lang="ts">
import { 
  ArrowRight, 
  Beaker, 
  ShieldCheck, 
  Microscope, 
  ThermometerSnowflake, 
  Droplets, 
  Activity,
  CheckCircle2,
  HardHat,
  Scale
} from 'lucide-vue-next'

const properties = [
  { title: "優異的機械強度", desc: "抗壓強度高於一般混凝土數倍，能承受重型機具與推高機頻繁碾壓而不破裂。", icon: HardHat },
  { title: "極佳的耐化學性", desc: "對多數酸鹼溶液、溶劑、機油具有極高的抵抗力，防止混凝土地基遭受腐蝕。", icon: Beaker },
  { title: "無縫高潔淨度", desc: "一體成型的塗層無接縫設計，不藏汙納垢，完全不會起塵，符合無塵室 Class 100 標準。", icon: Microscope },
  { title: "強悍的接著性", desc: "與水泥基材、鋼板金屬等皆具有非常優異的分子級附著力，不易發生剝離。", icon: ShieldCheck },
  { title: "優越的防水防滲", desc: "閉孔隙結構，完全阻絕水氣與液體向下滲透，保護底層鋼筋與基材。", icon: Droplets },
  { title: "穩定性與耐候", desc: "固化收縮率極低（<2%），硬化後尺寸安定，不易因溫差產生嚴重形變或龜裂。", icon: ThermometerSnowflake }
]

const specs = [
  { item: "抗壓強度 (Compressive Strength)", standard: "ASTM D695", value: "700 ~ 1,000 kg/cm²" },
  { item: "抗拉強度 (Tensile Strength)", standard: "ASTM D638", value: "300 ~ 500 kg/cm²" },
  { item: "抗折強度 (Flexural Strength)", standard: "ASTM D790", value: "400 ~ 600 kg/cm²" },
  { item: "表面硬度 (Shore D Hardness)", standard: "ASTM D2240", value: "80 ~ 85" },
  { item: "混凝土接著力 (Adhesion to Concrete)", standard: "ASTM D4541", value: "> 30 kg/cm² (混凝土破壞)" },
  { item: "耐磨耗性 (Abrasion Resistance)", standard: "ASTM D4060", value: "< 40 mg (CS-17, 1kg, 1000 cycles)" }
]
</script>

<template>
  <NuxtLayout>
    <!-- Hero Section -->
    <section class="relative bg-slate-900 border-b-4 border-yellow-500 overflow-hidden">
      <div class="absolute inset-0 z-0">
        <img 
          src="https://images.unsplash.com/photo-1581092160607-ee22621dd758?q=80&w=1920&auto=format&fit=crop" 
          alt="Epoxy Chemistry" 
          class="w-full h-full object-cover opacity-10 mix-blend-overlay grayscale"
        />
        <div class="absolute inset-0 bg-[linear-gradient(to_right,#ffffff0a_1px,transparent_1px),linear-gradient(to_bottom,#ffffff0a_1px,transparent_1px)] bg-[size:32px_32px]" />
      </div>

      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-32 md:py-40 flex flex-col items-center text-center">
        <div class="flex items-center gap-4 mb-6">
          <div class="h-1 w-12 bg-yellow-500" />
          <span class="text-yellow-500 font-mono uppercase tracking-[0.2em] text-sm font-bold">Resin Technology</span>
          <div class="h-1 w-12 bg-yellow-500" />
        </div>
        <h1 class="text-5xl md:text-7xl font-extrabold text-white mb-6 tracking-tight">
          環氧樹脂工程指南
        </h1>
        <p class="text-xl md:text-2xl text-slate-300 font-light max-w-3xl leading-relaxed">
          深入解析 EPOXY 地坪的化學特性、物理強度與專業施工工序。
        </p>
      </div>
    </section>

    <!-- Definition Section -->
    <section class="py-24 bg-white relative">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div>
            <div class="text-yellow-600 font-mono tracking-widest text-sm font-bold uppercase mb-4">01. What is Epoxy?</div>
            <h2 class="text-3xl lg:text-4xl font-extrabold text-slate-900 mb-6 tracking-tight">何謂環氧樹脂 (EPOXY)？</h2>
            <div class="space-y-6 text-slate-600 leading-relaxed text-lg text-justify">
              <p>
                <strong>環氧樹脂 (Epoxy Resin)</strong> 是一種含有兩個或多個環氧基團的高分子化合物。它屬於熱固性樹脂 (Thermosetting Polymer) 的一種，在未添加固化劑（硬化劑）之前，通常呈現黏稠的液態。
              </p>
              <p>
                當環氧樹脂主劑 (A劑) 與專用的胺類或聚醯胺類固化劑 (B劑) 依嚴格的比例混合後，會產生交聯反應 (Cross-linking) 並放熱，由液體逐漸聚合形成強韌的三維網狀固體結構。這過程不可逆，一旦硬化成型，便無法透過加熱使其熔化。
              </p>
              <p>
                正因為其硬化後結構極度緊密，EPOXY 地坪展現出絕佳的物理抗壓能力、耐化學酸鹼腐蝕性，且表面平滑無縫、不吸附灰塵，成為了台灣半導體廠、無塵室、醫療與食品生技廠的最嚴格標準配備。
              </p>
            </div>
          </div>
          <div class="relative">
            <div class="absolute -top-4 -left-4 w-32 h-32 bg-yellow-100 rounded-sm z-0"></div>
            <div class="absolute -bottom-4 -right-4 w-32 h-32 bg-slate-800 rounded-sm z-0"></div>
            <img src="https://images.unsplash.com/photo-1532094349884-543bc11b234d?q=80&w=800&auto=format&fit=crop" alt="Chemistry of Epoxy" class="relative z-10 w-full rounded-sm shadow-xl grayscale-[20%]" />
            <div class="absolute bottom-6 -left-10 bg-slate-900 border-l-4 border-yellow-500 p-6 shadow-2xl z-20 max-w-xs">
              <div class="flex items-start gap-4 text-white">
                <Activity class="w-8 h-8 text-yellow-500 shrink-0" />
                <div>
                  <h4 class="font-bold text-lg mb-1 relative underline decoration-yellow-500 underline-offset-4">三維交聯反應</h4>
                  <p class="text-xs text-slate-400 font-mono leading-relaxed mt-3">Cross-linking process forms an incredibly durable micro-structure.</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Properties Grid -->
    <section class="py-24 bg-slate-50 border-t border-slate-200">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <div class="text-yellow-600 font-mono tracking-widest text-sm font-bold uppercase mb-4">02. Core Characteristics</div>
          <h2 class="text-3xl font-extrabold text-slate-900 tracking-tight">六大核心物性優勢</h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="(prop, index) in properties" :key="index" class="bg-white p-8 border border-slate-200 hover:border-yellow-500 transition-colors shadow-sm relative group overflow-hidden">
            <div class="absolute top-0 right-0 w-16 h-16 bg-slate-50 opacity-0 group-hover:opacity-100 transition-opacity rounded-bl-full z-0" />
            <div class="relative z-10">
              <div class="w-12 h-12 bg-slate-900 border border-slate-800 flex items-center justify-center text-yellow-500 mb-6 group-hover:scale-110 transition-transform shadow-md">
                <component :is="prop.icon" class="w-6 h-6" />
              </div>
              <h3 class="text-xl font-bold text-slate-900 mb-3 group-hover:text-yellow-600 transition-colors">{{ prop.title }}</h3>
              <p class="text-slate-600 text-sm leading-relaxed">{{ prop.desc }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Technical Specs Table -->
    <section class="py-24 bg-slate-900 text-white relative overflow-hidden">
      <!-- Background blueprint grid -->
      <div class="absolute inset-0 bg-[linear-gradient(to_right,#1e293b_1px,transparent_1px),linear-gradient(to_bottom,#1e293b_1px,transparent_1px)] bg-[size:24px_24px]" />
      
      <div class="w-full h-1 bg-yellow-500 absolute top-0 left-0" />

      <div class="relative z-10 max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-12">
          <div class="flex justify-center mb-4"><Scale class="w-10 h-10 text-yellow-500" /></div>
          <div class="text-yellow-500 font-mono tracking-widest text-sm font-bold uppercase mb-4">03. Physical Parameters</div>
          <h2 class="text-3xl font-extrabold text-white tracking-tight leading-tight">標準技術規格數據表</h2>
          <p class="mt-4 text-slate-400 text-sm">此為標準工業級 EPOXY 平塗/流展工法之硬化測試參考值，實際數據因材料配方而異。</p>
        </div>

        <div class="bg-slate-950 border border-slate-700 rounded-sm shadow-2xl overflow-hidden">
          <table class="w-full text-left text-sm whitespace-nowrap">
            <thead class="bg-slate-900 border-b border-slate-700 text-slate-300 font-mono uppercase tracking-wider">
              <tr>
                <th scope="col" class="px-6 py-4">檢測項目</th>
                <th scope="col" class="px-6 py-4">測試標準</th>
                <th scope="col" class="px-6 py-4 text-yellow-500">標準數值範圍</th>
              </tr>
            </thead>
            <tbody class="divide-y divide-slate-800">
              <tr v-for="(spec, i) in specs" :key="i" class="hover:bg-slate-900/50 transition-colors">
                <td class="px-6 py-5 font-medium text-white">{{ spec.item }}</td>
                <td class="px-6 py-5 font-mono text-slate-400">{{ spec.standard }}</td>
                <td class="px-6 py-5 font-bold text-yellow-400">{{ spec.value }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </section>

    <!-- Deep Dive Process -->
    <section class="py-24 bg-white border-b border-slate-200">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="mb-16">
          <div class="text-yellow-600 font-mono tracking-widest text-sm font-bold uppercase mb-4">04. Engineering Process</div>
          <h2 class="text-3xl font-extrabold text-slate-900 tracking-tight">標準基材處理與完整鏝塗工序</h2>
        </div>

        <div class="space-y-12">
          <!-- Step A -->
          <div class="flex flex-col md:flex-row gap-8 items-start border-l-4 border-slate-200 pl-6 lg:pl-10 ml-4 hover:border-yellow-500 transition-colors py-4">
            <div class="md:w-1/3">
              <span class="text-6xl font-extrabold text-slate-100 block mb-2 font-mono leading-none">A</span>
              <h3 class="text-xl font-bold text-slate-900 mb-2 mt-4">基材診斷與素地整理 (Surface Preparation)</h3>
            </div>
            <div class="md:w-2/3 space-y-4 text-slate-600 text-[15px] leading-relaxed">
              <p>所有的失敗地坪有 80% 歸咎於基材處理不當。我們要求混凝土基底經過 28 天以上養護，含水率必須控制在 8% 以下，抗壓強度達 3,000 psi 以上。</p>
              <ul class="space-y-2 mt-4">
                <li class="flex items-start gap-2"><CheckCircle2 class="w-5 h-5 text-yellow-600 shrink-0 mt-0.5" /> <strong>研磨拋版：</strong>使用重型鎢鋼/鑽石研磨機，刨除表面的脆弱泥漿層（Laitance）、舊漆材、油汙。</li>
                <li class="flex items-start gap-2"><CheckCircle2 class="w-5 h-5 text-yellow-600 shrink-0 mt-0.5" /> <strong>修補縫隙：</strong>針對切割縫、不規則裂縫進行 V-Cut 切割，並使用高強度環氧樹脂砂漿先行填補平整。</li>
                <li class="flex items-start gap-2"><CheckCircle2 class="w-5 h-5 text-yellow-600 shrink-0 mt-0.5" /> <strong>吸塵除汙：</strong>使用工業級防爆吸塵器，將表面微麈徹底吸淨，確保無阻隔物。</li>
              </ul>
            </div>
          </div>

          <!-- Step B -->
          <div class="flex flex-col md:flex-row gap-8 items-start border-l-4 border-slate-200 pl-6 lg:pl-10 ml-4 hover:border-yellow-500 transition-colors py-4">
            <div class="md:w-1/3">
              <span class="text-6xl font-extrabold text-slate-100 block mb-2 font-mono leading-none">B</span>
              <h3 class="text-xl font-bold text-slate-900 mb-2 mt-4">高滲透底漆塗佈 (Primer Coating)</h3>
            </div>
            <div class="md:w-2/3 space-y-4 text-slate-600 text-[15px] leading-relaxed">
              <p>選用雙劑型高滲透力環氧底漆，利用滾筒均勻塗佈。底漆的任務在於深深滲入混凝土的微小毛細孔中封閉水氣，同時提供後續中塗層強悍的「分子化學鍵結力」，如同樹根緊緊抓牢土壤。</p>
            </div>
          </div>

          <!-- Step C -->
          <div class="flex flex-col md:flex-row gap-8 items-start border-l-4 border-slate-200 pl-6 lg:pl-10 ml-4 hover:border-yellow-500 transition-colors py-4">
            <div class="md:w-1/3">
              <span class="text-6xl font-extrabold text-slate-100 block mb-2 font-mono leading-none">C</span>
              <h3 class="text-xl font-bold text-slate-900 mb-2 mt-4">流展/厚塗砂漿中塗 (Mortar / Base Coat)</h3>
            </div>
            <div class="md:w-2/3 space-y-4 text-slate-600 text-[15px] leading-relaxed">
              <p>中塗層是決定地坪厚度與抗衝擊能力的核心。將環氧樹脂依比例混合石英砂，透過鏝刀手工均勻批刮或流展於地面。此層具備絕佳的抗壓乘載力，並能填平所有微小的高低差，創造絕對水平的基底。</p>
            </div>
          </div>

          <!-- Step D -->
          <div class="flex flex-col md:flex-row gap-8 items-start border-l-4 border-slate-200 pl-6 lg:pl-10 ml-4 hover:border-yellow-500 transition-colors py-4">
            <div class="md:w-1/3">
              <span class="text-6xl font-extrabold text-slate-100 block mb-2 font-mono leading-none">D</span>
              <h3 class="text-xl font-bold text-slate-900 mb-2 mt-4">平滑無縫面漆塗裝 (Top Coating)</h3>
            </div>
            <div class="md:w-2/3 space-y-4 text-slate-600 text-[15px] leading-relaxed">
              <p>待中層完全硬化並經細緻研磨後，施作高硬度面漆。此層帶來最終的色彩外觀亮度（亮面、半平光），並賦予優越的抗刮耗、耐酸鹼浸蝕及防塵能力。依需求可採用自平流展（自流平法，厚度>1mm）或滾塗法完成。</p>
            </div>
          </div>

        </div>
      </div>
    </section>

    <!-- Maintainance & CTA -->
    <section class="py-24 bg-slate-950 text-center relative overflow-hidden">
      <div class="absolute inset-0 z-0 bg-[radial-gradient(circle_at_center,rgba(234,179,8,0.05)_0%,transparent_60%)]"></div>
      
      <div class="relative z-10 max-w-4xl mx-auto px-4">
        <h2 class="text-3xl font-extrabold text-white mb-6">為您的廠區提供最高規格防護</h2>
        <p class="text-slate-400 text-lg mb-10 font-light leading-relaxed">
          不論是無塵室要求的極致平口防塵、還是重機具倉庫需要的高抗衝擊，俊泰工程團隊都能為您提供化學材料選定與標準化施工。
        </p>
        <NuxtLink 
          to="/contact" 
          class="inline-flex items-center gap-2 bg-yellow-500 text-slate-950 font-extrabold px-8 py-4 uppercase tracking-widest text-sm hover:bg-yellow-400 transition-colors shadow-lg shadow-yellow-500/20 rounded-sm"
        >
          聯絡工程師評估 <ArrowRight class="w-4 h-4" />
        </NuxtLink>
      </div>
    </section>

  </NuxtLayout>
</template>

<style scoped>
/* Scoped styles */
</style>
