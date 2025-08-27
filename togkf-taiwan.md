---
layout: default
title: TOGKF 台灣支部
permalink: /togkf-taiwan/
---
<div class="container-xxl py-5">
  <div class="container">
    <div class="section-header text-center mx-auto mb-5 wow fadeInUp" data-wow-delay="0.1s"
            style="max-width: 500px;">
      <h1 class="display-5 mb-3">TOGKF 台灣支部</h1>
      <p>TOGKF Taiwan Branch</p>
    </div>
    <div class="row g-5 align-items-center">
      <div class="col-lg-6 col-md-8 col-sm-12 wow fadeIn" data-wow-delay="0.1s">
        <div class="about-img position-relative overflow-hidden p-3">
          <img class="img-fluid rounded shadow-sm mx-auto d-block" 
               style="max-width: 60%; height: auto;" 
               src="{{ '/assets/img/about/wu_mengtsung_1.jpg' | relative_url }}">
        </div>
      </div>
      <div class="col-lg-6 wow fadeIn" data-wow-delay="0.5s">
        <h2 class="mb-1">Taiwan Chief Instructor Wu MengTsung Sensei</h2>
        <h1 class="display-6 mb-4">台灣支部代表 吳孟聰 先生</h1>

        <!-- 專業感：改為垂直時間軸（Timeline）呈現，強調年份與里程碑 -->
        {% include timeline.html items=site.data.timeline_wu %}
        <!-- 小註解：若日後要放完整履歷，可改用兩欄：左欄年份；右欄詳細描述。 -->
      </div>
    </div>
  </div>
</div>
