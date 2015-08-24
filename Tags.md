---
layout: page
title: "Tags"
description: "博客标签库"
header-img: "img/bay.jpg"
---



<!-- Page Header -->
<header class="intro-header">
    <div class="container">
        <div class="row">
            <div class="col-lg-8 col-lg-offset-2 col-md-10 col-md-offset-1">
                <div class="site-heading" id="tag-heading">
                    <h1>{% if page.title %}{{ page.title }}{% else %}{{ site.title }}{% endif %}</h1>
                    <span class="subheading">{{ page.description }}</span>
                </div>
            </div>
        </div>
    </div>
</header>

<!-- Main Content -->
<div class="container">
	<div class="row">
		<div class="col-lg-8 col-lg-offset-2 col-md-10 col-md-offset-1">
			<!-- {{content}} -->
            <!-- 标签云 -->
			<div id='tag_cloud' class="tags">
				{% for tag in site.tags %}
				<a href="#{{ tag[0] }}" title="{{ tag[0] }}" rel="{{ tag[1].size }}">{{ tag[0] }}</a>
				{% endfor %}
			</div>
            
            <blockquote class="tag-comments">

            </blockquote>
            
            <!-- 标签列表 -->
			{% for tag in site.tags %}
			<div class="one-tag-list">
			  	<span class="fa fa-tag listing-seperator" id="{{ tag[0] }}">{{ tag[0] }}</span>
				{% for post in tag[1] %}
				  <!-- <li class="listing-item">
				  <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
				  <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
				  </li> -->
				 <div class="post-preview">
				    <a href="{{ post.url | prepend: site.baseurl }}">
				        <h2 class="post-title">            {{ post.title }}
				        </h2>
				        {% if post.subtitle %}
				        <h3 class="post-subtitle">
				            {{ post.subtitle }}
				        </h3>
				        {% endif %}
				    </a>
				    <!-- <p class="post-meta">{{ post.date | date:"%Y-%m-%d" }}</p> -->
				</div>
				<hr>
				{% endfor %}
			</div>
			{% endfor %}

		</div>
	</div>
</div>