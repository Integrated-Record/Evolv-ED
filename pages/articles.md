---
layout: page
title: Article Index 
permalink: /articles/index/
hero_image: "/images/heros/free-photo-of-termeszet-viz-sziklak-moha.jpeg"
---


<!-- Read in dependencies for the table -->
<script src="{{site.url}}{{site.baseurl}}/assets/js/jquery-3.7.0.js"></script>  <!--Add JQuery-->
<script src="{{site.url}}{{site.baseurl}}/assets/js/jquery.dataTables.min.js"></script>
<link rel="stylesheet" type="text/css" href="{{site.url}}{{site.baseurl}}/assets/css/jquery.dataTables.min.css" />



<div class="content" markdown="1">
You can find all available articles on this page.
  
- Tutorials are organized into general *topics*. 
- Use the search bar to find tutorials based text.
- Click on resource buttons to learn more about them. Software resources are marked as blue tags, data resources with red: <span class="tag is-info">software</span> <span class="tag is-danger">data</span>

</div>

<br>

<div class="box">
  <h2 id="tutorials">All Articles</h2>
  <hr>
  <!-- Filter out the relevant tutorials-->

  <table class="display" id="my-table">
	<thead>
		<tr><th>Title</th><th>Date</th><th>Type</th><th>Topic(s)</th><th>Resources</th></tr>
	</thead>
	<tbody>
	<!-- go through all ttutorials -->
	  {% for tutorial in site.data.articles %}
		  <!-- find versions of this article -->
		{% assign thisTutorial = site.data.articleversions | where: 'tutorial', tutorial.id %}
		<!-- sort them by date and reverse, first is mot up-to-date -->
		{% assign sorted = thisTutorial | sort: 'datum' | reverse %}
		{% assign tv= sorted[0] %}
		  <tr style="min-height:200px">
			<td style="text-align: left"> 
				<div class="columns">
				<div class="column is-9">
				<a href="{{site.url}}{{site.baseurl}}/articles/{{tv.tutorial}}-{{tv.version}}.html">
				<p><strong>{{ tv.title }} </strong></p>
				</a>
				<div>
				{% for author in tv.authors %}
					{% unless forloop.last %}
						{{author}},&nbsp;
					{% else %}
						{{author}}
					{% endunless %}
				{% endfor %}
				</div>
				<p></p>
			  <div class="field is-grouped is-grouped-multiline">
			    <a href="https://doi.org/{{tv.doi}}">
					<div class="control">
						<div class="tags has-addons" style="margin-bottom:8px;flex-wrap:nowrap;padding-top:0.25rem">
							<span class="tag is-dark is-small" style="font-size:0.5rem">DOI</span>
							{%if tv.doi %}
							<span class="tag is-info is-small" style="font-size:0.5rem">{{tv.doi}}</span>
							{% else %}
							<span class="tag is-danger is-small" style="font-size:0.5rem">Not yet!</span>
							{% endif%}
						</div>
					</div>
				</a> 
				</div>
				<div class="tags">
				{% for tag in tv.tags %}
					<span class="tag is-white is-small">{{tag}}</span>
				{% endfor %}
				</div>
				</div>
				</div>
				</td>
			<td><i>{{tv.datum}}</i></td>
			<td>{{tutorial.type}}</td>
			<td>{{tv.topic}}</td>
			<td>
			  <div class="field is-grouped is-grouped-multiline">
			  {% for res in tv.dependencies%}
			  <div class="control">
				<a href="{{site.url}}{{site.baseurl}}/software/{{res.id | downcase}}.html"><div class="tags">
				  <!-- Search for the resource's long name -->
				  {% for thisRes in site.data.software %}
					<!-- If the resource is present in registry, showi it -->
					{% if thisRes.id == res.id %}
					  <!-- If there is a display name, show that, otherwise use ID -->
					  {% if thisRes.display%}
					<span class="tag is-info resourcetag">{{thisRes.display}}</span>
					  {% else %}
					<span class="tag is-info resourcetag">{{res.id}}</span>
					  {% endif %}
					{% endif %}
				  {% endfor %}
				</div></a>
			  </div>
			  {% endfor %}
			  </div>
			  <div class="field is-grouped is-grouped-multiline">
			{% for res in tv.data %}
			<div class="control">
				<a href="{{site.url}}{{site.baseurl}}/data/{{res.id | downcase}}.html"><div class="tags">
				<!-- Search for the resource's long name -->
				{% for thisRes in site.data.data %}
					<!-- If the resource is present in registry, showi it -->
					{% if thisRes.id == res.id %}
					<!-- If there is a display name, show that, otherwise use ID -->
					{% if thisRes.display%}
					<span class="tag is-danger resourcetag">{{thisRes.display}}</span>
					{% else %}
					<span class="tag is-danger resourcetag">{{res.id}}</span>
					{% endif %}
					{% endif %}
				{% endfor %}
				</div></a>
			  </div>
			  {% endfor %}
			  </div>
			</td>
		  </tr>
		{% endfor %}
	</tbody>
  </table>

<!-- </div>  close column -->
<!-- </div> close columns -->


</div> <!-- close content -->


<!-- Modification script for the data-table -->
<script>
new DataTable('#my-table');
</script>
