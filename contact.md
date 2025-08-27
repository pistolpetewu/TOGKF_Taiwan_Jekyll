---
layout: default
title: 聯絡方式
permalink: /contact/
---
<div class="container-xxl py-5">
  <div class="container">
    <div class="section-header text-center mx-auto mb-5 wow fadeInUp" data-wow-delay="0.1s"
            style="max-width: 500px;">
      <h1 class="display-5 mb-3">聯絡方式</h1>
    </div>
    <div class="row g-5 justify-content-center">
      <div class="col-lg-5 col-md-12 wow fadeInUp" data-wow-delay="0.1s">
        <div class="bg-light text-white d-flex flex-column justify-content-center h-100 p-5">
          <h5 class="text-dark">{{ site.data.site.name.chinese }}</h5>
          <p class="mb-5 text-dark">{{ site.data.site.name.dojo }}</p>
          <h5 class="text-dark">練習時間</h5>
          <p class="text-dark">{{ site.data.site.schedule.day1 }} {{ site.data.site.schedule.time1 }}</p>
          <p class="text-dark">{{ site.data.site.schedule.day2 }} {{ site.data.site.schedule.time2 }}</p>
          <p class="text-dark">{{ site.data.site.schedule.day3 }} {{ site.data.site.schedule.time3 }}</p>
          <p class="mb-5 text-dark"></p>
          <h5 class="text-dark">地址</h5>
          <p class="mb-5 text-dark"><i class="fa fa-map-marker-alt me-3"></i>{{ site.data.site.address.name }}</p>
          <!-- <h5 class="text-dark">電話</h5>
          <p class="mb-5 text-dark"><i class="fa fa-phone-alt me-3"></i>09ZZ-XXX-YYY</p> -->
          <h5 class="text-dark">電子郵件</h5>
          <p class="mb-5 text-dark"><i class="fa fa-envelope me-3"></i>{{ site.data.site.email }}</p>
          <h5 class="text-dark">追蹤我們</h5>
          <div class="d-flex pt-2">
            <a class="btn btn-square text-dark btn-outline-primary rounded-circle me-1" href="{{ site.data.site.social.facebook }}">
              <i class="fab fa-facebook-f"></i></a>
            <a class="btn btn-square text-dark btn-outline-primary rounded-circle me-1" href="{{ site.data.site.social.instagram }}">
              <i class="fab fa-instagram"></i></a>
            <a class="btn btn-square text-dark btn-outline-primary rounded-circle me-1" href="{{ site.data.site.social.line }}">
                <i class="fab fa-line"></i></a>
          </div>
        </div>
      </div>
      <div class="col-lg-7 col-md-12 wow fadeInUp" data-wow-delay="0.5s">
        <div class="position-relative overflow-hidden pe-0">
          <img class="img-fluid w-100" src="{{ '/assets/img/dojo.jpg' | relative_url }}">
        </div>
        <iframe class="w-100" style="height: 400px;" src="{{ site.data.site.address.map_embed }}" frameborder="0" allowfullscreen="" aria-hidden="false" tabindex="0"></iframe>
      </div>
    </div>
  </div>
</div>