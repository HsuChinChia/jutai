<script setup lang="ts">
import { ref } from 'vue'
import { MapPin, Phone, Mail, Clock, Send, CheckCircle2 } from 'lucide-vue-next'

const form = ref({
  name: '',
  email: '',
  phone: '',
  subject: '',
  message: ''
})

const isSubmitting = ref(false)
const isSubmitted = ref(false)

const handleSubmit = async () => {
  isSubmitting.value = true
  // Simulate API call
  await new Promise(resolve => setTimeout(resolve, 1500))
  isSubmitting.value = false
  isSubmitted.value = true
}
</script>

<template>
  <NuxtLayout>
    <!-- Hero Section -->
    <section class="relative h-[40vh] min-h-[300px] flex items-center justify-center overflow-hidden bg-slate-900">
      <div class="absolute inset-0 z-0 opacity-40">
        <img 
          src="https://picsum.photos/seed/contact/1920/1080?blur=2" 
          alt="Contact Us" 
          class="w-full h-full object-cover"
          referrerPolicy="no-referrer"
        />
      </div>
      <div class="absolute inset-0 bg-gradient-to-b from-slate-900/80 via-slate-900/60 to-slate-900 z-10" />
      
      <div class="relative z-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <div class="animate-fade-in-up">
          <h1 class="text-4xl md:text-6xl font-bold text-white mb-6">
            聯絡我們
          </h1>
          <p class="text-xl text-slate-300 max-w-2xl mx-auto font-light leading-relaxed">
            無論是工程諮詢、報價需求，或有任何疑問，歡迎隨時與我們聯繫。
          </p>
        </div>
      </div>
    </section>

    <!-- Contact Content -->
    <section class="py-24 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16">
          
          <!-- Contact Info -->
          <div class="animate-fade-in-left">
            <h2 class="text-3xl font-bold text-slate-900 mb-8">
              俊泰工程有限公司
            </h2>
            <p class="text-slate-600 mb-12 leading-relaxed">
              我們擁有專業的技術團隊與豐富的施工經驗，致力於為客戶提供最優質的地坪解決方案。期待與您的合作！
            </p>

            <div class="space-y-8">
              <div class="flex items-start gap-6 group">
                <div class="w-12 h-12 bg-blue-50 rounded-xl flex items-center justify-center text-blue-600 group-hover:bg-blue-600 group-hover:text-white transition-colors duration-300 flex-shrink-0">
                  <MapPin :size="24" />
                </div>
                <div>
                  <h3 class="text-lg font-bold text-slate-900 mb-1">公司地址</h3>
                  <p class="text-slate-600">高雄市前鎮區瑞祥街142號</p>
                  <a 
                    href="https://maps.google.com/?q=高雄市前鎮區瑞祥街142號" 
                    target="_blank"
                    class="text-sm text-blue-500 hover:text-blue-700 mt-2 inline-block"
                  >
                    在 Google 地圖上查看
                  </a>
                </div>
              </div>

              <div class="flex items-start gap-6 group">
                <div class="w-12 h-12 bg-blue-50 rounded-xl flex items-center justify-center text-blue-600 group-hover:bg-blue-600 group-hover:text-white transition-colors duration-300 flex-shrink-0">
                  <Phone :size="24" />
                </div>
                <div>
                  <h3 class="text-lg font-bold text-slate-900 mb-1">聯絡電話</h3>
                  <p class="text-slate-600">07-726-1010</p>
                  <p class="text-sm text-slate-500 mt-1">週一至週五 08:30 - 17:30</p>
                </div>
              </div>

              <div class="flex items-start gap-6 group">
                <div class="w-12 h-12 bg-blue-50 rounded-xl flex items-center justify-center text-blue-600 group-hover:bg-blue-600 group-hover:text-white transition-colors duration-300 flex-shrink-0">
                  <Mail :size="24" />
                </div>
                <div>
                  <h3 class="text-lg font-bold text-slate-900 mb-1">電子信箱</h3>
                  <p class="text-slate-600">juntai.wu01@gmail.com</p>
                  <a 
                    href="mailto:juntai.wu01@gmail.com" 
                    class="text-sm text-blue-500 hover:text-blue-700 mt-2 inline-block"
                  >
                    寄送郵件
                  </a>
                </div>
              </div>
            </div>

            <!-- Map Placeholder -->
            <div class="mt-12 rounded-2xl overflow-hidden shadow-lg border border-slate-200 h-64 bg-slate-100 relative group">
              <img 
                src="https://picsum.photos/seed/map/800/400?blur=1" 
                alt="Map Location" 
                class="w-full h-full object-cover opacity-80 group-hover:opacity-100 transition-opacity"
                referrerPolicy="no-referrer"
              />
              <div class="absolute inset-0 flex items-center justify-center pointer-events-none">
                <div class="bg-white/90 backdrop-blur px-4 py-2 rounded-lg shadow-sm text-sm font-medium text-slate-700 flex items-center gap-2">
                  <MapPin :size="16" class="text-red-500" /> 高雄市前鎮區
                </div>
              </div>
            </div>
          </div>

          <!-- Contact Form -->
          <div class="bg-slate-50 rounded-3xl p-8 md:p-12 shadow-sm border border-slate-100 animate-fade-in-right">
            <div v-if="!isSubmitted">
              <h3 class="text-2xl font-bold text-slate-900 mb-6">線上諮詢</h3>
              <form @submit.prevent="handleSubmit" class="space-y-6">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                  <div>
                    <label for="name" class="block text-sm font-medium text-slate-700 mb-2">姓名</label>
                    <input 
                      v-model="form.name"
                      type="text" 
                      id="name" 
                      required
                      class="w-full px-4 py-3 rounded-lg border border-slate-200 focus:ring-2 focus:ring-blue-500 focus:border-transparent outline-none transition-all bg-white"
                      placeholder="您的稱呼"
                    />
                  </div>
                  <div>
                    <label for="phone" class="block text-sm font-medium text-slate-700 mb-2">聯絡電話</label>
                    <input 
                      v-model="form.phone"
                      type="tel" 
                      id="phone" 
                      required
                      class="w-full px-4 py-3 rounded-lg border border-slate-200 focus:ring-2 focus:ring-blue-500 focus:border-transparent outline-none transition-all bg-white"
                      placeholder="09xx-xxx-xxx"
                    />
                  </div>
                </div>

                <div>
                  <label for="email" class="block text-sm font-medium text-slate-700 mb-2">電子信箱</label>
                  <input 
                    v-model="form.email"
                    type="email" 
                    id="email" 
                    required
                    class="w-full px-4 py-3 rounded-lg border border-slate-200 focus:ring-2 focus:ring-blue-500 focus:border-transparent outline-none transition-all bg-white"
                    placeholder="example@email.com"
                  />
                </div>

                <div>
                  <label for="subject" class="block text-sm font-medium text-slate-700 mb-2">諮詢主旨</label>
                  <select 
                    v-model="form.subject"
                    id="subject" 
                    class="w-full px-4 py-3 rounded-lg border border-slate-200 focus:ring-2 focus:ring-blue-500 focus:border-transparent outline-none transition-all bg-white text-slate-600"
                  >
                    <option value="" disabled selected>請選擇諮詢項目</option>
                    <option value="quote">工程報價</option>
                    <option value="consult">技術諮詢</option>
                    <option value="site">預約勘查</option>
                    <option value="other">其他事項</option>
                  </select>
                </div>

                <div>
                  <label for="message" class="block text-sm font-medium text-slate-700 mb-2">諮詢內容</label>
                  <textarea 
                    v-model="form.message"
                    id="message" 
                    rows="5" 
                    required
                    class="w-full px-4 py-3 rounded-lg border border-slate-200 focus:ring-2 focus:ring-blue-500 focus:border-transparent outline-none transition-all bg-white resize-none"
                    placeholder="請簡述您的需求、場地狀況或預計施工面積..."
                  ></textarea>
                </div>

                <button 
                  type="submit" 
                  :disabled="isSubmitting"
                  class="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-4 rounded-xl transition-all shadow-lg shadow-blue-600/20 flex items-center justify-center gap-2 disabled:opacity-70 disabled:cursor-not-allowed"
                >
                  <span v-if="isSubmitting">傳送中...</span>
                  <span v-else class="flex items-center gap-2">確認送出 <Send :size="18" /></span>
                </button>
              </form>
            </div>

            <!-- Success State -->
            <div v-else class="h-full flex flex-col items-center justify-center text-center py-12">
              <div class="w-20 h-20 bg-green-100 rounded-full flex items-center justify-center text-green-600 mb-6 animate-bounce">
                <CheckCircle2 :size="40" />
              </div>
              <h3 class="text-2xl font-bold text-slate-900 mb-4">訊息已送出！</h3>
              <p class="text-slate-600 mb-8 max-w-xs mx-auto">
                感謝您的諮詢，我們已收到您的訊息。專員將於 1-2 個工作天內與您聯繫。
              </p>
              <button 
                @click="isSubmitted = false; form = { name: '', email: '', phone: '', subject: '', message: '' }"
                class="text-blue-600 font-medium hover:text-blue-800 underline"
              >
                發送另一則訊息
              </button>
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

.animate-fade-in-left {
  animation: fadeInLeft 0.8s ease-out forwards;
  opacity: 0;
  transform: translateX(-20px);
}

.animate-fade-in-right {
  animation: fadeInRight 0.8s ease-out forwards;
  opacity: 0;
  transform: translateX(20px);
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInLeft {
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeInRight {
  to {
    opacity: 1;
    transform: translateX(0);
  }
}
</style>
