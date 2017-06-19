---
layout: default
title: MacroSquad
permalink: /macrosquad/
order: 4
---

Schedule and updates for MacroSquad:

* TOC
{:toc}

# Schedule

<script src="https://code.jquery.com/jquery-3.1.1.min.js"   
integrity="sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8="  crossorigin="anonymous"></script>
<script type="text/javascript" src="/scripts/moment.min.js"></script>
<script src="//cdnjs.cloudflare.com/ajax/libs/fullcalendar/3.2.0/fullcalendar.min.js"></script>
<link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/fullcalendar/3.2.0/fullcalendar.min.css">
<link rel="stylesheet" media="print" href="//cdnjs.cloudflare.com/ajax/libs/fullcalendar/3.2.0/fullcalendar.print.css">

<script>
$(document).ready(function() {

	$('#calendar').fullCalendar({
		events:'/calendar-data/'
	})

});

</script>


<!-- {% for event in site.events %}
{{event.title}} {{event.event_date}}<br/>
{% endfor %} -->

<div id="calendar"></div>

# Posts

<ul class="posts">
  {% for post in site.posts %}
	{% if post.macrosquad_event %}
  <li>
    <br>
    <h3>
      <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </h3>
    <span class="post-meta">{{ post.date | date: "%b %-d, %Y %l:%m %p" }}</span>
    <hr id="line">
    <div class="content">
      {{ post.excerpt }}
    </div>
    <br>
  </li>
	{% endif %}
  {% endfor %}
</ul>

# Notes

## Macroeconomic Theory I, ECON 605

* [ECON 605 Stolyarov notes](https://umich.box.com/s/3x06wji3k2mkmwrcbdggwlrq410vtg0g)
* [ECON 605 Stolyarov review](https://umich.box.com/s/14r5lvjjoq9wwz0d6mor8jn49v6vig5g)
* [ECON 605 Leahy notes](https://umich.box.com/s/qwizsx7l6ejrnzdunmrckznnwhge2h9y)

## Macroeconomic Theory II, ECON 607

Coming soon...
