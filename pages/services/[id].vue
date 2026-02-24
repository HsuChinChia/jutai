<script setup lang="ts">
import { useRoute } from 'vue-router'
import { ArrowLeft, CheckCircle2, Factory, ShieldAlert, Sparkles, Building2, Beaker, HardHat, Layers } from 'lucide-vue-next'

const route = useRoute()
const serviceId = route.params.id as string

// Comprehensive database of service details for the engineering pages
const servicesDb: Record<string, any> = {
  '1': {
    title: 'EPOXY 無塵地坪系統',
    subtitle: '為高科技產業量身打造的極致潔淨解決方案',
    icon: Sparkles,
    heroImage: 'https://images.unsplash.com/photo-1541888086425-d81bb19240f5?q=80&w=1920&auto=format&fit=crop',
    overview: '針對精密電子零組件製造、半導體晶圓廠、以及生技製藥產業所設計的高性能地坪系統。不僅提供完全無縫、不起塵的表面，更能藉由加入導電微粒，快速安全地將靜電導入接地系統，避免靜電放電(ESD)對精密儀器造成不可逆的損害。',
    specs: [
      { label: '標準施工厚度', value: '2.0 mm - 3.0 mm' },
      { label: '表面電阻值 (導電型)', value: '10⁴ ~ 10⁶ Ω' },
      { label: '潔淨度標準', value: '符合 Class 100 ~ 100K' },
      { label: '抗壓強度', value: '> 500 kg/cm²' },
      { label: '表面硬度 (Shore D)', value: '80 - 85' },
      { label: '完全固化時間', value: '7 天 (25°C)' }
    ],
    features: [
      '極致平滑無縫面，杜絕細菌與微塵藏匿',
      '高分子聚合技術，抗剝離接著力強',
      '可選配高光澤或消光表面',
      '優異的抗化學品潑濺能力'
    ],
    applications: ['半導體晶圓廠', 'SMT 表面黏著產線', '生技製藥無塵室', '精密光學儀器廠', '醫療開刀房'],
    process: [
      { step: '01', title: '素地處理', desc: '真空強力研磨機去除水泥浮漿，徹底擴創開口毛細孔。' },
      { step: '02', title: '防潮底塗封閉', desc: '塗佈高滲透環氧樹脂底漆，深入混凝土內部鞏固基層。' },
      { step: '03', title: '銅箔與導電底塗 (選配)', desc: '鋪設接地銅網，並全面塗佈碳黑導電底漆。' },
      { step: '04', title: '流展面塗鏝平', desc: '使用帶齒鏝刀均勻塗佈自流平 EPOXY 面漆，釋放氣泡並自動整平。' }
    ]
  },
  '2': {
    title: '耐酸鹼 FRP 地坪防護',
    subtitle: '為高腐蝕風險環境建立的終極防禦網',
    icon: Beaker,
    heroImage: 'https://images.unsplash.com/photo-1581092160562-40aa08e78837?q=80&w=1920&auto=format&fit=crop',
    overview: '玻璃纖維強化塑膠 (FRP) 搭配頂級乙烯基樹脂，專為必須承受強酸、強鹼、溶劑及高溫侵蝕的嚴苛環境設計。多層積層結構不僅提供卓越的防滲漏阻絕層，其抗拉強度更能有效防止因廠房震動或熱脹冷縮造成的底材龜裂。',
    specs: [
      { label: '標準施工厚度', value: '3.0 mm - 5.0 mm' },
      { label: '耐酸鹼性', value: '耐 98% 硫酸、30% 氫氧化鈉' },
      { label: '抗拉強度', value: '> 1,200 kg/cm²' },
      { label: '耐熱溫度', value: '連續 80°C / 瞬間 120°C' },
      { label: '積層構造', value: '2 ~ 3 層玻璃纖維網' },
      { label: '透水率', value: '0% (完全阻絕)' }
    ],
    features: [
      '超強抗拉伸與抗衝擊能力',
      '無縫一體成型，百分百防漏水',
      '耐受多種極端化學品浸泡',
      '可做防滑壓花或平滑表面處理'
    ],
    applications: ['化學原物料儲槽區', '電鍍與表面處理廠', '印刷電路板(PCB)濕製程區', '廢水處理池', '食品發酵廠'],
    process: [
      { step: '01', title: '基材整平除汙', desc: '徹底清除油汙與化學殘留，確保素地乾燥且毛細孔完全敞開。' },
      { step: '02', title: '耐酸鹼底塗', desc: '塗佈高滲透型耐酸鹼底漆，提供後續樹脂層強大接著力。' },
      { step: '03', title: '玻璃纖維積層', desc: '鋪設玻璃纖維網 (Chopped Strand Mat)，並多次手工積層塗佈乙烯基樹脂。' },
      { step: '04', title: '面塗防護', desc: '塗佈具高緻密性的耐酸鹼面漆，包覆纖維，達到完全平整的防護表面。' }
    ]
  },
  '3': {
    title: '重載 U-MORTAR 砂漿',
    subtitle: '為極度嚴苛的重工業輾壓環境而生',
    icon: Building2,
    heroImage: 'https://images.unsplash.com/photo-1504917595217-d4f3915ce83c?q=80&w=1920&auto=format&fit=crop',
    overview: '將高強度環氧樹脂與精密級配的石英砂均勻混合，以鏝塗方式施工的重防腐、極重載地坪系統。不僅具有極高的抗壓與抗衝擊強度，能抵禦 3~5 噸以上電動堆高機的頻繁急停與輾壓，且能有效修補嚴重凹凸不平的舊有廠房地面。',
    specs: [
      { label: '標準施工厚度', value: '3.0 mm - 10.0 mm' },
      { label: '抗壓強度', value: '> 800 kg/cm²' },
      { label: '接著強度', value: '大於混凝土內聚強度' },
      { label: '耐衝擊性', value: '極佳 (1kg 鋼球 1m 落下無裂痕)' },
      { label: '體積收縮率', value: '< 0.1%' },
      { label: '使用年限預估', value: '10 年以上 (依使用強度)' }
    ],
    features: [
      '超厚實防護層，極致耐重磨耗',
      '有效修補嚴重破損之劣質混凝土',
      '高韌性配方，吸收機具震動',
      '抗金屬切削液與機械機油浸蝕'
    ],
    applications: ['重型機械製造與組裝廠', '模具沖壓廠', '軍工與航太零件廠', '汽車製造與維修廠', '高頻繁物流轉運中心'],
    process: [
      { step: '01', title: '重型研磨與V-Cut', desc: '使用破壞型研磨機削平骨材，針對既有裂縫切割 V-Cut 溝槽。' },
      { step: '02', title: '深層固化底膠', desc: '塗佈環氧樹脂接著底漆，並針對坑洞先行局部砂漿填補。' },
      { step: '03', title: '樹脂砂漿主層鋪設', desc: '均勻拌合環氧樹脂與特選石英砂，透過人工或機具重力鏝平。' },
      { step: '04', title: '晶潤面漆封層', desc: '塗佈高硬度環氧面塗，封閉砂漿毛細孔，形成易於清潔的光滑或止滑表面。' }
    ]
  },
  '4': {
    title: 'PU 頂樓防水工程',
    subtitle: '對抗極端氣候的柔性防水護盾',
    icon: Layers,
    heroImage: 'https://images.unsplash.com/photo-1621035043831-2fb07cd6fbcf?q=80&w=1920&auto=format&fit=crop',
    overview: '聚氨酯 (PU) 防水系統擁有極佳的彈性與伸長率，是建築物屋頂、露台防水的黃金標準。它能在建築物因日夜溫差產生的熱脹冷縮，或是輕微地震引發的結構細微裂縫中，維持防水層的完整性，達到滴水不漏的長期保護。',
    specs: [
      { label: '標準施工厚度', value: '2.0 mm - 3.0 mm' },
      { label: '斷裂伸長率', value: '> 450%' },
      { label: '抗拉強度', value: '> 25 kg/cm²' },
      { label: '耐候性 (UV)', value: '極佳 (搭配抗 UV 面漆)' },
      { label: '抗龜裂能力', value: '可跨越 2mm 結構裂縫' },
      { label: '適用底材', value: '混凝土、柏油、鐵皮金屬' }
    ],
    features: [
      '無接縫一體成型防水塗膜',
      '優越的物理彈性，抗震防裂',
      '耐水長期浸泡，不水解',
      '可選配反射隔熱型面漆 (Cool Roof)'
    ],
    applications: ['商業大樓頂樓', '住宅公寓屋頂', '戶外露台與中庭花園', '室內外游泳池基層', '空中停車場'],
    process: [
      { step: '01', title: '素地清理與導角', desc: '徹底清除舊有防水層與青苔，落水口周邊與女兒牆直角處進行泥作導角。' },
      { step: '02', title: 'PU 專用底塗', desc: '塗佈單液型或雙液型 PU 滲透底漆，確實封底增加附著力。' },
      { step: '03', title: 'PU 彈性中塗 (兩道)', desc: '分兩次均勻鋪設具高延展性的黑膠或綠膠 PU 中塗防水層。' },
      { step: '04', title: '抗 UV 面塗', desc: '待中塗固化後，塗抹耐熱抗紫外線的 PU 面漆，保護中塗層免於粉化。' }
    ]
  },
  '5': {
    title: '止滑車道地坪',
    subtitle: '確保行車動線安全的高抓地力表面',
    icon: HardHat,
    heroImage: 'https://images.unsplash.com/photo-1590623668817-adfc1a1795ca?q=80&w=1920&auto=format&fit=crop',
    overview: '不論是室內地下室車道還是迎雨的戶外坡道，車道專用止滑地坪能大幅增加車胎與地面之間的摩擦係數。透過鋪撒級配金鋼砂或石英砂，提供卓越的防滑效果，並能有效降低輪胎轉向摩擦所產生的尖銳噪音。',
    specs: [
      { label: '表面摩擦係數 (BPN)', value: '> 65 (高防滑標準)' },
      { label: '骨材種類', value: '石英砂 / 氧化鋁金鋼砂' },
      { label: '抗壓強度', value: '> 600 kg/cm²' },
      { label: '噪音降低率', value: '降低轉彎尖銳聲 80%' },
      { label: '坡度適應', value: '可施作於 >15% 陡坡' },
      { label: '完工通車時間', value: '一般車輛 48 小時後' }
    ],
    features: [
      '明確的雙色動線與警示區塊規劃',
      '消除傳統 EPOXY 常見的嘰嘰剎車聲',
      '抗汽車機油、煞車油滴落侵蝕',
      '雨天不打滑，大幅提升行車安全'
    ],
    applications: ['商辦與豪宅地下停車場', '大型購物中心室內車道', '物流轉運站卸貨區坡道', '重型機車測試道', '加油站前區'],
    process: [
      { step: '01', title: '舊標線與油汙刨除', desc: '以洗地機及研磨機徹底清除地面油垢與舊有熱壓反光標線。' },
      { step: '02', title: '高強接著底塗', desc: '塗佈強效底漆，確保後續的高強度輾壓拉扯不會造成脫層。' },
      { step: '03', title: '止滑中塗與散砂', desc: '塗佈中塗層的同時，透過設備或人工均勻滿撒分級防滑砂材。' },
      { step: '04', title: '耐磨包覆面漆', desc: '塗佈兩道高硬度車道面漆，將砂粒牢牢包覆鎖緊並進行標線標尺放樣。' }
    ]
  },
  '6': {
    title: '建築外牆防汙保護',
    subtitle: '抵抗歲月侵蝕，長保建築外觀如新',
    icon: ShieldAlert,
    heroImage: 'https://images.unsplash.com/photo-1558227691-41ea78d1f631?q=80&w=1920&auto=format&fit=crop',
    overview: '台灣氣候多雨且空氣中富含汙染物與酸性物質，外牆容易因雨水沖刷形成黑色髒汙。我們的外牆防汙保護系統採用奈米級技術，在不改變原建築材質外觀的前提下，賦予牆面極佳的撥水性與自潔能力，讓髒汙不再深入石材或塗料毛細孔。',
    specs: [
      { label: '防護機制', value: '高滲透奈米透氣薄膜' },
      { label: '撥水角度', value: '> 110 度 (荷葉效應)' },
      { label: '透氣性', value: '高 (允許底材水氣逸散)' },
      { label: '耐黃變測試', value: '通過 2000 小時 QUV 測試' },
      { label: '外觀改變', value: '透明無膜感 (不改變原色)' },
      { label: '耐洗刷性', value: '可承受高壓水槍清洗' }
    ],
    features: [
      '防潑水抗沾黏，雨水沖刷即發揮自潔效用',
      '防止酸雨侵蝕外皮，延緩石材與清水模白樺現象',
      '高透氣性防止塗膜內部蓄積水氣導致起泡鼓起',
      '抗紫外線，保護底漆不褪色黃變'
    ],
    applications: ['高級住宅大樓外牆', '清水模建築外觀', '飯店與商業大樓帷幕', '歷史古蹟石材保護', '公共藝術裝置'],
    process: [
      { step: '01', title: '外牆高壓清洗', desc: '使用高壓清洗機徹底清除外牆的粉塵、青苔與既有水垢。' },
      { step: '02', title: '裂縫與帷幕填縫補強', desc: '檢視外牆並進行必要的矽利康 (Silicone) 更新與細微裂縫注射。' },
      { step: '03', title: '防汙劑噴塗 (第一道)', desc: '使用無氣噴塗機由下往上均勻噴塗第一道奈米防汙撥水劑。' },
      { step: '04', title: '防汙劑噴塗 (第二道)', desc: '趁第一道未完全乾燥前("濕碰濕"工法)，再次十字交叉噴塗確認完全被吸收。' }
    ]
  }
}

const service = servicesDb[serviceId]
</script>

<template>
  <NuxtLayout>
    <div v-if="service" class="bg-slate-50 min-h-screen">
      <!-- Minimal Header -->
      <div class="bg-slate-900 border-b border-slate-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4">
          <NuxtLink to="/services" class="inline-flex items-center gap-2 text-slate-400 hover:text-white transition-colors text-sm font-bold tracking-widest uppercase">
            <ArrowLeft :size="16" /> Back to Solutions
          </NuxtLink>
        </div>
      </div>

      <!-- Hero Section -->
      <section class="bg-slate-900 pt-16 pb-24 border-b-4 border-yellow-600 relative overflow-hidden">
        <div class="absolute inset-0 z-0">
          <img 
            :src="service.heroImage" 
            :alt="service.title" 
            class="w-full h-full object-cover opacity-20 grayscale mix-blend-overlay"
            referrerPolicy="no-referrer"
          />
          <div class="absolute inset-0 bg-gradient-to-t from-slate-900 via-slate-900/80 to-transparent" />
          <div class="absolute inset-0 bg-[linear-gradient(to_right,#ffffff05_1px,transparent_1px),linear-gradient(to_bottom,#ffffff05_1px,transparent_1px)] bg-[size:40px_40px]" />
        </div>

        <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="flex items-center gap-4 mb-6">
            <div class="w-16 h-16 bg-yellow-600 rounded-sm flex items-center justify-center border border-yellow-500 shadow-xl">
              <component :is="service.icon" class="w-8 h-8 text-white" />
            </div>
            <div>
              <span class="text-yellow-500 font-mono uppercase tracking-[0.2em] text-sm font-bold flex items-center gap-2">
                Tech Spec <span class="bg-slate-800 text-slate-300 px-2 py-0.5 rounded-sm">ID: 0{{ serviceId }}</span>
              </span>
            </div>
          </div>
          <h1 class="text-4xl md:text-5xl lg:text-6xl font-extrabold text-white mb-6 tracking-tight max-w-4xl">
            {{ service.title }}
          </h1>
          <p class="text-xl text-slate-300 font-light border-l-2 border-yellow-500 pl-4 max-w-2xl leading-relaxed">
            {{ service.subtitle }}
          </p>
        </div>
      </section>

      <!-- Content Grid -->
      <section class="py-16">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
            
            <!-- Left Column: Overview & Process -->
            <div class="lg:col-span-8 space-y-16">
              
              <!-- System Overview -->
              <div>
                <h2 class="text-2xl font-bold text-slate-900 mb-6 flex items-center gap-3">
                  <div class="w-2 h-6 bg-yellow-600" />系統概述
                </h2>
                <p class="text-slate-600 leading-relaxed text-lg">
                  {{ service.overview }}
                </p>
              </div>

              <!-- Application Process -->
              <div>
                <h2 class="text-2xl font-bold text-slate-900 mb-8 flex items-center gap-3">
                  <div class="w-2 h-6 bg-yellow-600" />標準施工剖面與流程
                </h2>
                <div class="space-y-6">
                  <div 
                    v-for="(step, index) in service.process" 
                    :key="index"
                    class="bg-white border border-slate-200 p-6 rounded-sm shadow-sm flex flex-col sm:flex-row gap-6 hover:border-yellow-300 transition-colors"
                  >
                    <div class="flex-shrink-0">
                      <div class="text-4xl font-mono font-bold text-slate-200 tracking-tighter">{{ step.step }}</div>
                    </div>
                    <div>
                      <h4 class="text-lg font-bold text-slate-900 mb-2">{{ step.title }}</h4>
                      <p class="text-slate-600 text-sm leading-relaxed">{{ step.desc }}</p>
                    </div>
                  </div>
                </div>
              </div>

              <!-- Advantages -->
              <div>
                <h2 class="text-2xl font-bold text-slate-900 mb-6 flex items-center gap-3">
                  <div class="w-2 h-6 bg-yellow-600" />工程優勢
                </h2>
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                  <div v-for="feat in service.features" :key="feat" class="bg-white border border-slate-200 p-4 rounded-sm flex items-start gap-3">
                    <CheckCircle2 :size="20" class="text-yellow-600 flex-shrink-0 mt-0.5" />
                    <span class="text-slate-700 text-sm font-medium">{{ feat }}</span>
                  </div>
                </div>
              </div>
            </div>

            <!-- Right Column: Tech Specs & Target Audience (Sticky) -->
            <div class="lg:col-span-4">
              <div class="sticky top-24 space-y-8">
                
                <!-- Technical Specifications Dashboard -->
                <div class="bg-slate-900 rounded-sm border border-slate-800 shadow-xl overflow-hidden">
                  <div class="bg-slate-950 px-6 py-4 border-b border-slate-800 flex justify-between items-center">
                    <h3 class="text-white font-bold tracking-widest uppercase text-sm flex items-center gap-2">
                      <Factory :size="16" class="text-yellow-500" /> 系統技術參數
                    </h3>
                  </div>
                  <div class="p-6">
                    <ul class="space-y-5">
                      <li v-for="spec in service.specs" :key="spec.label" class="border-b border-slate-800 pb-4 last:border-0 last:pb-0">
                        <div class="text-[11px] text-slate-500 font-mono tracking-widest uppercase mb-1">{{ spec.label }}</div>
                        <div class="text-white font-bold text-sm">{{ spec.value }}</div>
                      </li>
                    </ul>
                  </div>
                </div>

                <!-- Applications -->
                <div class="bg-white rounded-sm border border-slate-200 p-6 shadow-sm">
                  <h3 class="text-slate-900 font-bold mb-4 flex items-center gap-2">
                    適用場域
                  </h3>
                  <div class="flex flex-wrap gap-2">
                    <span 
                      v-for="app in service.applications" 
                      :key="app" 
                      class="bg-slate-100 text-slate-700 border border-slate-200 px-3 py-1.5 rounded-sm text-xs font-bold"
                    >
                      {{ app }}
                    </span>
                  </div>
                </div>

                <!-- CTA -->
                <div class="bg-yellow-600 rounded-sm p-6 text-white text-center shadow-lg shadow-yellow-900/20">
                  <h3 class="font-bold text-lg mb-2">需要這項工程服務？</h3>
                  <p class="text-yellow-100 text-xs mb-6">我們的工程師將為您的廠房環境進行現場評估，並提供最適合的施作計畫與報價。</p>
                  <NuxtLink to="/contact" class="block w-full bg-white text-yellow-600 font-bold py-3 text-sm rounded-sm hover:bg-slate-900 hover:text-white transition-colors">
                    立即聯絡勘估
                  </NuxtLink>
                </div>

              </div>
            </div>

          </div>
        </div>
      </section>

    </div>

    <!-- 404 State -->
    <div v-else class="min-h-screen flex items-center justify-center bg-slate-50">
      <div class="text-center">
        <h2 class="text-4xl font-bold text-slate-900 mb-4">服務項目不存在</h2>
        <p class="text-slate-600 mb-8">您尋找的工程系統規格可能已經下架或網址錯誤。</p>
        <NuxtLink to="/services" class="bg-yellow-600 text-white px-6 py-3 rounded-sm font-bold hover:bg-slate-900 transition-colors">
          返回全方位解決方案
        </NuxtLink>
      </div>
    </div>
  </NuxtLayout>
</template>

<style scoped>
/* Scoped styles if needed */
</style>
