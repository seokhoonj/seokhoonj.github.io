---
layout: post
title: Django 템플릿 언어
category: Django
tags: [Django, template, 템플릿]
published: true
comments: true
---


변수
---
1. 변수는 {{ 변수 }}와 같은 모양, 템플릿 엔진이 변수를 만나면, 평가하여 그 결과로 치환  
2. 변수명은 영문자와 밑줄로 구성  
3. 변수명에는 공백이나 특수문자를 사용할 수 없음  
4. 점(.)은 변수의 속성에 접근할 때 사용 ( {{ section.title }} 은 section 개체의 title 속성으로 치환)  
5. 변수가 존재하지 않을 경우, 템플릿 시스템은 TEMPATE_STRING_IF_INVALID 설정값을 삽입하는데 그 기본값은 공백문자임  


필터
---
1. default: 변수가 false 또는 비어 있는 경우, 지정된 default를 사용, 그렇지 않으면 변수의 값을 사용
 - value가 없으면 "nothing"

```
{{ value|default:"nothing" }}
```
2. length: 값의 길이를 반환, 문자열과 목록에 대하여 사용
 - ['a', 'b', 'c', 'd']는 4

```python
{{ value|length }}
```

3. striptags: 모든 HTML 태그를 제거
 - "<b>Joel</b> <button>is</button> a <span>slug</span>"는 "Joel is a slug"

```python
{{ value|striptags }}
```


태그
---
1. for: 배열의 각 원소에 대하여 루프, 예를 들어, athlete_list에 들어 있는 선수의 목록을 출력하려면,
```python
<ul>
{% for athlete in athlete_list %}
    <li>{{ athlete.name }}</li>
{% endfor %}
</ul>
```

2. if and else: 변수를 평가하여, 변수가 "true"이면 블록의 컨텐츠를 표시
 - athlete_list가 비어있지 않다면, {{ athlete_list|length }} 변수에 의하여 선수의 숫자가 출력
```python
{% if athlete_list %}
    Number of athlete: {{ athlete_list|length }}
{% else %}
    No athletes
{% endif %}
```

3. if and else + for in endfor
```python
{% if athlete_list|length > 1 %}
   Team: {% for athlete in athlete_list %} ... {% endfor %}
{% else %}
   Athlete: {{ athlete_list.0.name }}
{% endif %}
```
