---
layout: page
title: blog
permalink: /blog
weight: 1
---

<!-- Page Header -->
<div class="container text-center align-middle justify-content-md-center">
    <div class="row row-cols-md-3 row-cols-sm-1">
        {% for post in site.posts %}
        <div class="col-sm">
            <div class="card text-center" style="width: 18rem;">
                <div class="card-body card-title">
                    <a href="{{ post.url }}"><h3>{{ post.title }}</h3></a>
                    <p class="card-text"> {{ post.excerpt }} </p>
                    <a href="{{ post.url }}">Read More</a><br>
                    <div class="date card-subtitle mb-2 text-muted">
                        {% if page.subtitle %}
                        {{ page.subtitle }}
                        {% endif %}
                        {% include read_time.html content=page.content %}<br>
                        Posted by <a
                            href="{{ post.url }}">{% if page.author %}{{ page.author }}{% else %}{{ site.author.name }}{% endif %}</a>
                        <br>on {{ post.date | date: '%B %d, %Y @ %H:%M' }}
                    </div>
                </div>
            </div>
            {% endfor %}
        </div>
    </div>
    <hr>
    <div class="clearfix">
        {% if page.previous.url %}
        <a class="btn btn-primary float-left"
            href="{{ page.previous.url | prepend: site.baseurl | replace: '//', '/' }}" data-toggle="tooltip"
            data-placement="top" title="{{ page.previous.title }}">&larr; Previous<span class="d-none d-md-inline">
                Post</span></a>
        {% endif %}
        {% if page.next.url %}
        <a class="btn btn-primary float-right" href="{{ page.next.url | prepend: site.baseurl | replace: '//', '/' }}"
            data-toggle="tooltip" data-placement="top" title="{{ page.next.title }}">Next<span
                class="d-none d-md-inline">
                Post</span> &rarr;</a>
        {% endif %}
    </div>
</div>
