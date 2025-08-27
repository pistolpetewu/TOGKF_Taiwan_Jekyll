---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: 首頁
---
<!-- Masonry News Wall Start -->
<div class="container-fluid py-5">
  <div class="container">
    <div class="section-header text-center mx-auto mb-4" style="max-width: 640px;">
      <h1 class="display-5 mb-2">最新消息 / 動態牆</h1>
      <p class="text-muted">Facebook．Blogger．Instagram</p>
    </div>

    <!-- 資訊牆：純 CSS columns，不需 JS -->
    <div class="masonry wow fadeInUp" data-wow-delay="0.1s">

      <!-- 形象照 1：照片 + Slogan -->
      <div class="masonry-item">
        <div class="card border-0 shadow-sm mb-4">
          <img src="{{ '/assets/img/carousel-4.jpg' | relative_url }}" class="card-img-top" alt="形象照1" loading="lazy">
          <div class="card-body">
            <h5 class="card-title mb-1">沖繩剛柔流空手道</h5>
            <p class="card-text text-muted mb-0">最早命名的空手道流派，跨越百年以上的歷史。</p>
          </div>
        </div>
      </div>
      <!-- 形象照 2：照片 + Slogan -->
      <div class="masonry-item">
        <div class="card border-0 shadow-sm mb-4">
          <img src="{{ '/assets/img/carousel-3.jpg' | relative_url }}" class="card-img-top" alt="形象照2" loading="lazy">
          <div class="card-body">
            <h5 class="card-title mb-1">追求和平的武道</h5>
            <p class="card-text text-muted mb-0">互相敬重、修練心性、培養健康的體魄。</p>
          </div>
        </div>
      </div>
      
      <!-- Facebook 卡片（放大版） -->
      <div class="masonry-item">
        <div class="card border-0 shadow-sm mb-4">
          <div class="fb-embed-wrapper">
            <iframe
              src="https://www.facebook.com/plugins/page.php?href=https%3A%2F%2Fwww.facebook.com%2FOkinawaGojuRyuKaratedoHigaonnaDojo.tw%2F&tabs=timeline&width=900&height=720&small_header=false&adapt_container_width=true&hide_cover=false&show_facepile=true"
              scrolling="no" frameborder="0" allowfullscreen
              allow="autoplay; clipboard-write; encrypted-media; picture-in-picture; web-share"></iframe>
          </div>
          <div class="card-body text-center">
            <a class="btn btn-outline-primary rounded-pill px-3"
               href="{{ site.data.site.social.facebook }}"
               target="_blank" rel="noopener">造訪粉絲頁</a>
          </div>
        </div>
      </div>

      <!-- Blogger 最新三篇（清單版，佔滿整列） -->
      <div class="masonry-item w-100">
        <div class="card border-0 shadow-sm mb-4">
          <div class="card-header bg-white">
            <h5 class="mb-0">Blogger 最新文章</h5>
          </div>
          <div class="card-body p-0">
            <ul id="blogger-list" class="list-group list-group-flush"></ul>
          </div>
        </div>
      </div>

      <!-- Blogger 說明卡（放在清單下方） -->
      <div class="masonry-item">
        <div class="card border-0 shadow-sm mb-4">
          <div class="card-body">
            <h5 class="card-title">Blogger 部落格</h5>
            <p class="card-text text-muted">支部長的練功心得、教學札記與活動紀錄。</p>
            <a class="btn btn-outline-secondary rounded-pill px-3"
               href="{{ site.data.site.external.blogger }}" target="_blank" rel="noopener">前往閱讀</a>
          </div>
        </div>
      </div>
      <!-- Instagram 卡片 -->
      <div class="masonry-item">
        <div class="card border-0 shadow-sm mb-4">
          <div class="ratio ratio-1x1">
            <!-- Instagram embed：改成你的帳號網址 -->
            <iframe
              src="{{ site.data.site.social.instagram }}embed" 
              allowtransparency="true" frameborder="0" scrolling="no"
              style="width:100%; height:100%; border:0; overflow:hidden;"
              allowfullscreen>
            </iframe>
          </div>
          <div class="card-body text-center">
            <h5 class="card-title mb-2">Instagram</h5>
            <p class="card-text text-muted">追蹤我們的最新活動花絮。</p>
            <a class="btn btn-outline-danger rounded-pill px-3"
              href="{{ site.data.site.social.instagram }}"
              target="_blank" rel="noopener">前往 IG</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
<!-- Masonry News Wall End -->

<!-- Blogger 最新N篇（JSONP，避免 CORS） -->
<script>
(function() {
  const ul = document.getElementById("blogger-list");
  if (!ul) return;

  const cbName = "renderBloggerList_" + Math.random().toString(36).slice(2);
  window[cbName] = function(data) {
    try {
      const entries = (data.feed && data.feed.entry) ? data.feed.entry.slice(0,1) : [];
      if (!entries.length) {
        ul.innerHTML = `<li class="list-group-item text-muted">目前沒有可顯示的文章</li>`;
        return;
      }
      const items = entries.map(e => {
        const title = (e.title && e.title.$t) || "無標題";
        const linkObj = (e.link || []).find(l => l.rel === "alternate");
        const link = linkObj ? linkObj.href : "#";
        const published = (e.published && e.published.$t ? e.published.$t.slice(0,10) : "");
        const summary = ((e.summary && e.summary.$t) || "")
                          .replace(/<[^>]*>/g, "").slice(0, 110) + "…";
        const content = (e.content && e.content.$t) || "";
        let img = null;
        const m = content.match(/<img[^>]+src="([^">]+)"/i);
        if (m) img = m[1];
        else if (e["media$thumbnail"] && e["media$thumbnail"].url) img = e["media$thumbnail"].url;

        return `
          <li class="list-group-item">
            <a href="${link}" target="_blank" rel="noopener" class="text-reset text-decoration-none">
              <div class="d-flex align-items-start">
                ${img ? `<img src="${img}" alt="${title}" class="blogger-thumb me-3">` : ""}
                <div class="flex-grow-1">
                  <div class="small text-muted mb-1">${published}</div>
                  <h6 class="mb-1">${title}</h6>
                  <p class="mb-0 text-muted">${summary}</p>
                </div>
              </div>
            </a>
          </li>
        `;
      }).join("");

      ul.innerHTML = items;
    } catch (err) {
      console.error(err);
      ul.innerHTML = `<li class="list-group-item text-muted">無法解析 Blogger 文章</li>`;
    } finally {
      try { delete window[cbName]; } catch(e) { window[cbName] = undefined; }
      setTimeout(() => script.remove(), 0);
    }
  };

  const script = document.createElement("script");
  script.src = "https://sanchintw.blogspot.com/feeds/posts/default"
             + "?max-results=3&alt=json-in-script&callback=" + cbName;
  script.async = true;
  script.onerror = function() {
    ul.innerHTML = `<li class="list-group-item text-muted">無法載入 Blogger 文章</li>`;
    try { delete window[cbName]; } catch(e) { window[cbName] = undefined; }
  };
  document.head.appendChild(script);
})();
</script>
