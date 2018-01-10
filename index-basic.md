---
layout: default
---

<div class="text-center mt-5 mb-5">
  <img src="https://www.arduino.cc/en/uploads/Main/Create-software1.svg" class="rounded-circle" alt="GoyoBot logo">
  <h1>GoyoBot</h1>
</div>


<div class="mx-auto" style="max-width: 768px;">

{% for member in site.data.members %}

<p class="lead">{{ member[1].name }}</p>
  
<div class="row justify-content-start m-2 m-sm-3">
{% for smr in member[1].authors %}
  <div class="col-3 col-md-2 p-1">
    <div class="text-center">
    <div class="card bg-transparent border-0 mx-auto" style="max-width: 90px;">
      <img class="card-img-top" src="{% if site.data[smr] %}{{ site.data[smr].icon }}{% else %}{{ site.baseurl }}/assets/img/members/default.png{% endif %}" alt="Card image cap">
      <div class="card-block">
        <p class="card-title">{% if site.data[smr] %}{{ site.data[smr].shortname }}{% else %}{{ smr }}{% endif %}</p>
      </div>
    </div>
    </div>
  </div>
{% endfor %}
</div>

{% endfor %}



</div>