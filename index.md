---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
---
{% assign previous_post_date = "0000" %}
{% assign general_posts = site.posts %}

<ul>
  {% for post in  general_posts limit:20 %}
    {% assign current_post_date =  post.date | date: "%m%y" %}

    {% if current_post_date != previous_post_date %}
        <h2> {{ post.date | date: "%B, %Y" }} </h2>
    {% endif %}

    <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a><br>

    <div class="mobile visible-sm visible-xs"><br></div>

    {% assign previous_post_date = current_post_date %}

    {% if current_post_date != previous_post_date %}
        <br>
    {% endif %}
  {% endfor %}

</ul>

