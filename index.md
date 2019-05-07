---
layout: page
title: Reservation List
permalink: /
---
{% assign domains = site.reservations|sort:"name"|group_by:"name" %}
<table>
  <thead>
    <tr><th>Name</th><th>Claimant</th><th>Address</th></tr>
  </thead>
  <tbody>
    {% for domain in domains %}
      {% for claim in domain.items %}
        <tr>
          {% if forloop.first %}
            <td rowspan="{{domain.items|size}}">{{domain.name}}.eth</td>
          {% endif %}
          <td>{{claim.site}}</td>
          <td><a href="https://etherscan.io/address/{{claim.owner}}">{{claim.owner}}</a></td>
        </tr>
      {% endfor %}
    {% endfor %}
  </tbody>
</table>
