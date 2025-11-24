---
layout: home
author_profile: true
header:
  overlay_color: "#4B6CB7"
  overlay_filter: "0.5"
  overlay_image: /assets/images/header-bg.jpg  # 배경 이미지 (선택)
  actions:
    - label: "블로그 둘러보기"
      url: "/categories/"
excerpt: "AI를 더 쉽고 안전하게, 모두를 위한 AI 서비스 가이드"
intro: 
  - excerpt: '최신 AI 서비스 사례와 트렌드, 정책을 한눈에 확인하세요.'
feature_row:
  - image_path: /assets/images/ai-service-icon.png
    alt: "AI 서비스"
    title: "AI 서비스 사례"
    excerpt: "최신 AI 서비스를 소개합니다."
    url: "/categories/#ai-서비스-사례"
    btn_label: "더 보기"
    btn_class: "btn--primary"
  - image_path: /assets/images/ai-tech-icon.png
    alt: "AI 기술"
    title: "AI 기술 트렌드"
    excerpt: "최신 AI 기술 동향과 발전 방향을 정리합니다."
    url: "/categories/#기술-트렌드"
    btn_label: "더 보기"
    btn_class: "btn--primary"
  - image_path: /assets/images/ai-policy-icon.png
    title: "AI 관련 정책"
    excerpt: "국내외 AI 정책과 규제 동향을 알아봅니다."
    url: "/categories/#AI-정책"
    btn_label: "더 보기"
    btn_class: "btn--primary"
---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}