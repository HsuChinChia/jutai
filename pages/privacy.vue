<template>
  <NuxtLayout>
    <section class="py-24 bg-white min-h-screen">
      <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="animate-fade-in-up">
          <h1 class="text-4xl font-bold text-slate-900 mb-8">隱私權政策</h1>
          <div class="space-y-6 text-slate-600 leading-relaxed font-light">
            <p>
              為了讓您能夠安心的使用本網站的各項服務與資訊，特此向您說明本網站的隱私權保護政策，以保障您的權益，請您詳閱下列內容：
            </p>
            
            <h2 class="text-2xl font-bold text-slate-800 mt-8 mb-4">一、隱私權保護政策的適用範圍</h2>
            <p>
              隱私權保護政策內容，包括本網站如何處理在您使用網站服務時收集到的個人識別資料。隱私權保護政策不適用於本網站以外的相關連結網站，也不適用於非本網站所委託或參與管理的人員。
            </p>
            
            <h2 class="text-2xl font-bold text-slate-800 mt-8 mb-4">二、個人資料的蒐集、處理及利用方式</h2>
            <ul class="list-disc pl-6 space-y-2">
              <li>當您造訪本網站或使用本網站所提供之功能服務時，我們將視該服務功能性質，請您提供必要的個人資料，並在該特定目的範圍內處理及利用您的個人資料。</li>
              <li>本網站在您使用聯絡信箱、問卷調查等互動性功能時，會保留您所提供的姓名、電子郵件地址、聯絡方式及使用時間等。</li>
              <li>於一般瀏覽時，伺服器會自行記錄相關行徑，包括您使用連線設備的IP位址、使用時間、使用的瀏覽器、瀏覽及點選資料記錄等，做為我們增進網站服務的參考依據。</li>
            </ul>
            
            <h2 class="text-2xl font-bold text-slate-800 mt-8 mb-4">三、資料之保護</h2>
            <p>
              本網站主機均設有防火牆、防毒系統等相關的各項資訊安全設備及必要的安全防護措施，加以保護網站及您的個人資料採用嚴格的保護措施，只由經過授權的人員才能接觸您的個人資料。
            </p>

            <h2 class="text-2xl font-bold text-slate-800 mt-8 mb-4">四、網站對外的相關連結</h2>
            <p>
              本網站的網頁提供其他網站的網路連結，您也可經由本網站所提供的連結，點選進入其他網站。但該連結網站不適用本網站的隱私權保護政策。
            </p>

            <h2 class="text-2xl font-bold text-slate-800 mt-8 mb-4">五、隱私權保護政策之修正</h2>
            <p>
              本網站隱私權保護政策將因應需求隨時進行修正，修正後的條款將刊登於網站上。
            </p>
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
