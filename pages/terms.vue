<template>
  <NuxtLayout>
    <section class="py-24 bg-white min-h-screen">
      <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="animate-fade-in-up">
          <h1 class="text-4xl font-bold text-slate-900 mb-8">服務條款</h1>
          <div class="space-y-6 text-slate-600 leading-relaxed font-light">
            <p>
              歡迎使用俊泰工程有限公司提供的網站服務。當您存取或使用本網站時，即表示您同意遵守以下服務條款：
            </p>
            
            <h2 class="text-2xl font-bold text-slate-800 mt-8 mb-4">一、接受條款</h2>
            <p>
              進入本網站，即表示您理解並同意接受本條款及條件。若您不同意這些條款的任何一部分，請勿使用本網站的各項服務。
            </p>
            
            <h2 class="text-2xl font-bold text-slate-800 mt-8 mb-4">二、網站使用與規範</h2>
            <ul class="list-disc pl-6 space-y-2">
              <li>您同意僅基於合法目的使用本網站，不得進行任何可能損害、癱瘓、超載或削弱本網站伺服器或網路的行動。</li>
              <li>不得利用本網站從事任何侵犯他人權益或違法之行為。</li>
              <li>本網站呈現之產品資訊與技術規格僅供參考，若有工程需求，應以雙方簽訂之正式合約為準。</li>
            </ul>
            
            <h2 class="text-2xl font-bold text-slate-800 mt-8 mb-4">三、智慧財產權</h2>
            <p>
              本網站上所有內容，包含但不限於文字、圖片、照片、標誌、版面設計、影音及軟體等，其相關智慧財產權均受中華民國法律及國際版權法保護，未經本公司事前書面同意，任何人不得逕自使用、修改、重製、公開播送、改作、散布或公開傳輸。
            </p>

            <h2 class="text-2xl font-bold text-slate-800 mt-8 mb-4">四、免責聲明</h2>
            <p>
              本網站提供的所有資訊按「現況」及「現有」基礎提供。本公司不保證網站功能不會中斷或不受病毒等有害組件的影響。我們保留隨時修改、暫停或終止網站部分或全部功能的權利。
            </p>

            <h2 class="text-2xl font-bold text-slate-800 mt-8 mb-4">五、準據法與管轄權</h2>
            <p>
              本服務條款之解釋與適用，以及與本服務條款有關的爭議，均應依照中華民國法律予以處理，並以台灣高雄地方法院為第一審管轄法院。
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
