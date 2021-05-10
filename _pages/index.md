---
layout: default
title: Home
id: home
redirect_from: "/en"
permalink: /
---

<div>
  <p>
    <b>Dr Daniel Nemenyi 🙋🏻‍♂️</b>
  </p>

  <p>
    Hi! I teach in the <a target="_blank" rel="noopener" href="https://www.kcl.ac.uk/people/daniel-nemenyi">Department of Digital Humanities</a>, King's College London, and I'm an editor of the journal <a target="_blank" rel="noopener" href="https://www.radicalphilosophy.com/">Radical Philosophy</a>. I completed my MA and PhD at the <a target="_blank" rel="noopener" href="https://www.kingston.ac.uk/faculties/kingston-school-of-art/research-and-innovation/crmep/">Centre for Research in Modern European Philosophy (CRMEP)</a> at Kingston University, calling my thesis <em>What is an internet? Norbert Wiener and the society of control</em> (2019). I enjoy writing about code, especially its conceptual history, and writing in code, especially in LaTeX, Python and Emacs. My pronouns are he/him. I'm sporadically active on <a target="_blank" rel="noopener" href="https://gitlab.com/klinamen0">Gitlab</a>, <a target="_blank" rel="noopener" href="https://github.com/danielnemenyi">GitHub</a> and <a target="_blank" rel="noopener" href="https://twitter.com/DanielNemenyi">Twitter</a> (direct messages are open 👋).
  </p>

  <div>

    <div class="grid-element">
      <p><b>Blog ☕</b></p>
      {% assign post_limit = 6 %}
      {% for post in site.posts limit: post_limit %}
      <div class="list-entry">
        <div><a class="internal-link" href="{{ post.url }}">{{ post.title }}</a> <span class="faded">({{ post.date | date: "%-d %b %Y" }})</span></div>
        <div>{{ post.subtitle }}</div>
      </div>
      {% endfor %}

	  {% assign additional_posts = site.posts.size | minus: post_limit %}
	  {% if additional_posts > 0 %}
      <p>
        <a class="internal-link" href="/blog">I wrote {{ site.posts.size | minus: post_limit }} more posts</a>.
        This blog is also available as <a class="internal-link" target="_blank" href="/rss.xml">RSS</a> and <a class="internal-link" target="_blank" href="/feed.json">JSON</a> feeds.
      </p>
	  {% endif %}
    </div>

	<div class="grid-element">
      <p><b>Talks 📢</b></p>
      {% assign talk_limit = 6 %}
      {% for talk in site.data.talks limit: talk_limit %}
      <div class="list-entry">
        <div>{{ talk.date | date: "%-d %b %Y" }}: {{ talk.title }} <a class="internal-link" href="{{ talk.url }}">{{ talk.url-title }}</a></div>
        <div class="faded">@ {{ talk.event }}, {{ talk.location }}</div>
      </div>
      {% endfor %}

	  {% assign additional_talks = site.data.talks.size | minus: talk_limit %}
	  {% if additional_talks > 0 %}
      <p>
        <a class="internal-link" href="/talks">I gave {{ site.data.talks.size | minus: talk_limit }} more talks</a>.
      </p>
	  {% endif %}
    </div>

    <div class="grid-element">
      <p><b>Publications 🖊</b></p>

      {% assign publications_limit = 5 %}
      {% for publication in site.data.publications limit: publications_limit %}
      <div class="list-entry">
        <div>
		{% if publication.url %}
			<a target="_blank" rel="noopener" href="{{ publication.url }}">{{ publication.title }}</a>
		{% else %}
			{{ publication.title }}
		{% endif %}

	        <span class="faded">{{ publication.month }} {{ publication.year }}</span>
		</div>

	   <div class="faded"><em>{{ publication.publisher }}</em></div>

	   {% if publication.note %}
		   <div class="faded">{{ publication.note }}</div>
	   {% endif %}


        <div>{{ publication.description_html }}</div>
      </div>
      {% endfor %}

      {% assign additional_publications = site.data.publications.size | minus: publications_limit %}
      {% if additional_publications > 0 %}
      <div>
        <p>{{ additional_publications }}
          <a class="internal-link" href="/publications">
            View all publications ({{ additional_publications }} more publications)
          </a>
        </p>
      </div>
      {% endif %}
    </div>

    <div class="grid-element">
      <p><b>Projects 🎣</b></p>

      {% assign project_limit = 4 %}
      {% for project in site.data.projects limit: project_limit %}
      <div class="list-entry">
        <div><a target="_blank" rel="noopener" href="{{ project.url }}">{{ project.name }}</a> <span class="faded">({{ project.year_from }}-{{ project.year_to }})</span></div>
        <div>{{ project.description_html }}</div>
      </div>
      {% endfor %}

      {% assign additional_projects = site.data.projects.size | minus: project_limit %}
      {% if additional_projects > 0 %}
      <div>
        <p>
          <a class="internal-link" href="/projects">
            View all projects ({{ additional_projects }} more projects)
          </a>
        </p>
      </div>
      {% endif %}
    </div>
  </div>
</div>
