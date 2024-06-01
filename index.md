---
layout: home
---

<div class="latest-div">
	{% assign latest = site.illusts | last %}

	<a href="{{ latest.url }}">
		<h2 class="post-title">{{ latest.title | escape }}</h2>
		<p class="post-meta">
			<time datetime="{{ latest.date | date_to_xmlschema }}">
				{{ latest.date | date: site.date_format }}
			</time>
		</p>

		{% include img_art.html page=latest %}

		<p>-</p>

		<div>{{ latest.content }}</div>
	</a>
</div>

<style>
	.post-title, .post-meta {
		margin-top: 0.25em;
		margin-bottom: 0.25em;

		display: inline;
	}

	.latest-div img {
		width: 100%;
		max-height: 50vh;
		object-fit: contain;
	}

	.latest-div a {
		text-decoration: none;
	}
</style>