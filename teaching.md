---
layout: default
title: Teaching
permalink: /teaching/
---

<div class="container">

 <header class="page-header">
 <p class="kicker">// Teaching</p>
 <p class="lead">
 Courses taught by the PI at the University of Houston, Department of
 Information Science Technology, Cullen College of Engineering.
 </p>
 </header>

 <div class="courses-list">
 {% for course in site.data.courses %}
 {% assign level_class = "course-level-ug" %}
 {% if course.level contains "Grad" %}{% assign level_class = "course-level-grad" %}{% endif %}
 <article class="course" data-pattern="{{ course.pattern | default: 'dots' }}">

 <div class="course-pattern" aria-hidden="true">
 {% case course.pattern %}
 {% when "dots" %}
 <svg viewBox="0 0 600 400" xmlns="http://www.w3.org/2000/svg">
 <defs><pattern id="cp-dots-{{ forloop.index }}" width="20" height="20" patternUnits="userSpaceOnUse"><circle cx="2" cy="2" r="1" fill="#C8102E"/></pattern></defs>
 <rect width="600" height="400" fill="url(#cp-dots-{{ forloop.index }})"/>
 </svg>
 {% when "diag" %}
 <svg viewBox="0 0 600 400" xmlns="http://www.w3.org/2000/svg">
 <defs><pattern id="cp-diag-{{ forloop.index }}" width="14" height="14" patternUnits="userSpaceOnUse" patternTransform="rotate(45)"><line x1="0" y1="0" x2="0" y2="14" stroke="#C8102E" stroke-width="1"/></pattern></defs>
 <rect width="600" height="400" fill="url(#cp-diag-{{ forloop.index }})"/>
 </svg>
 {% when "hex" %}
 <svg viewBox="0 0 600 400" xmlns="http://www.w3.org/2000/svg">
 <defs><pattern id="cp-hex-{{ forloop.index }}" width="28" height="32" patternUnits="userSpaceOnUse"><polygon points="14,0 28,8 28,24 14,32 0,24 0,8" fill="none" stroke="#C8102E" stroke-width="0.7"/></pattern></defs>
 <rect width="600" height="400" fill="url(#cp-hex-{{ forloop.index }})"/>
 </svg>
 {% when "lines" %}
 <svg viewBox="0 0 600 400" xmlns="http://www.w3.org/2000/svg">
 <g stroke="#C8102E" stroke-width="0.7" fill="none">
 <line x1="0" y1="80" x2="600" y2="160"/>
 <line x1="0" y1="200" x2="600" y2="100"/>
 <line x1="0" y1="280" x2="600" y2="320"/>
 <line x1="100" y1="0" x2="500" y2="400"/>
 <line x1="500" y1="0" x2="100" y2="400"/>
 </g>
 </svg>
 {% when "globe" %}
 <svg viewBox="0 0 600 400" xmlns="http://www.w3.org/2000/svg">
 <g stroke="#C8102E" stroke-width="0.7" fill="none">
 <ellipse cx="300" cy="200" rx="260" ry="80"/>
 <ellipse cx="300" cy="200" rx="260" ry="160"/>
 <ellipse cx="300" cy="200" rx="80" ry="260"/>
 <ellipse cx="300" cy="200" rx="160" ry="260"/>
 </g>
 </svg>
 {% when "binary" %}
 <svg viewBox="0 0 600 400" xmlns="http://www.w3.org/2000/svg">
 <g font-family="ui-monospace, monospace" font-size="13" fill="#C8102E">
 <text x="20" y="40">01001011 10110010 11010010</text>
 <text x="60" y="80">11010010 00111101 01001011</text>
 <text x="20" y="120">10110010 00101101 11010010</text>
 <text x="80" y="160">01101111 11010010 10110010</text>
 <text x="20" y="200">11010010 01001011 00111101</text>
 <text x="60" y="240">10110010 11010010 00101101</text>
 <text x="20" y="280">01001011 10110010 11010010</text>
 <text x="80" y="320">11010010 00111101 01001011</text>
 <text x="20" y="360">10110010 00101101 11010010</text>
 </g>
 </svg>
 {% else %}
 <svg viewBox="0 0 600 400" xmlns="http://www.w3.org/2000/svg">
 <defs><pattern id="cp-fb-{{ forloop.index }}" width="20" height="20" patternUnits="userSpaceOnUse"><circle cx="2" cy="2" r="1" fill="#C8102E"/></pattern></defs>
 <rect width="600" height="400" fill="url(#cp-fb-{{ forloop.index }})"/>
 </svg>
 {% endcase %}
 </div>

 <div class="course-book-col">
 {% if course.book_image %}
 <figure class="book-figure">
 <img src="{{ course.book_image | relative_url }}" alt="{{ course.title }} textbook cover" loading="lazy">
 {% if course.book_authors or course.book_edition %}
 <figcaption>
 {% if course.book_edition %}<span>{{ course.book_edition }}</span>{% endif %}
 {% if course.book_authors %}<span>{{ course.book_authors }}</span>{% endif %}
 </figcaption>
 {% endif %}
 </figure>
 {% else %}
 <div class="book">
 <div class="book-spine"></div>
 <div class="book-cover">
 <p class="book-code">{{ course.code }}</p>
 <p class="book-title">{{ course.title }}</p>
 <p class="book-label">Textbook</p>
 </div>
 </div>
 {% endif %}
 </div>

 <div class="course-content">
 <div class="course-meta-row">
 <span class="course-code-tag">{{ course.code }}</span>
 <span class="course-level {{ level_class }}">{{ course.level }}</span>
 </div>
 <h2>{{ course.title }}</h2>
 <p class="course-description">{{ course.description }}</p>
 {% if course.topics %}
 <div class="course-topics">
 {% for topic in course.topics %}<span>{{ topic }}</span>{% endfor %}
 </div>
 {% endif %}
 {% if course.semesters %}
 <div class="course-semesters">
 <p class="course-semesters-label">{{ course.semesters.size }} {% if course.semesters.size == 1 %}semester{% else %}semesters{% endif %}</p>
 <div class="course-semester-chips">
 {% for sem in course.semesters %}<span>{{ sem }}</span>{% endfor %}
 </div>
 </div>
 {% endif %}
 </div>

 </article>
 {% endfor %}
 </div>

</div>
