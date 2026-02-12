---
layout: default
title: "Posts"
lang: ko
---

# Session Docs

AI Agent 실습 노트와 챕터별 가이드를 정리합니다.
Copilot Studio로 Agent를 만들고, 테스트하고, 배포하는 흐름을 따라갑니다.

---

## 오늘의 하이라이트

> “Agent는 질문에 답하는 것에서 끝나지 않고, 실제 업무를 처리합니다.”

---

## 주제별 글

{% assign ordered = site.category_order %}
{% for cat in ordered %}
	{% assign cat_posts = site.categories[cat] %}
	{% if cat_posts %}
	<h3>{{ site.category_labels[cat] | default: cat }}</h3>
	<div class="post-grid">
		{% for post in cat_posts %}
			<article class="post-card">
				<h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
				<div class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</div>
				<p>{{ post.summary | default: post.excerpt | strip_html | truncate: 140 }}</p>
				{% if post.tags %}
				<div class="post-tags">
					{% for tag in post.tags %}
						<span class="post-tag">#{{ tag }}</span>
					{% endfor %}
				</div>
				{% endif %}
			</article>
		{% endfor %}
	</div>
	{% endif %}
{% endfor %}

---

## 데모 섹션

### 빠른 시작

1. Copilot Studio 접속
2. Pre-built Agent 생성
3. Knowledge 연결
4. 테스트 후 게시

### 샘플 Q&A

- Q: “사내 와이파이 접속 방법 알려줘.”
- A: “IT Helpdesk Assistant가 내부 문서를 참조해 단계별로 안내합니다.”

---

## 다음 스텝

- 실습용 문서 업로드
- SharePoint 연동 확인
- Custom Agent 프롬프트 정리
