---
layout: regular
title: Database
subTitle: What data is stored
---


# Data Ownership
We create a dedicated database for each one of our clients. It means that other clients cannot access your data, never. To illustrate better, imagine that two customers want to track the same keyword : well, our robots will still crawl twice and save each data in the two separated database.  
#### => Your account, your data.

<hr>

# Tables

There are 2 sort of data in DGM databases

- **Results** : Product & ranking information coming from the Amazon platform (crawled by robots)
- **Reports** : Sales Analytics coming the [Amazon Advertising plateform](https://advertising.amazon.com/)


### Results

Here is what the data looks like:

<table>
  {% for row in site.data.bqresults %}
    {% if forloop.first %}
    <tr style="margin-left:5px;margin-right:5px;background-color:#72b1df">
      {% for pair in row %}
        <th style="padding:5px;">{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}

    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}
  {% endfor %}
</table>



### Reports

Here is what the data looks like:

<table>
  {% for row in site.data.bqreports %}
    {% if forloop.first %}
    <tr style="margin-left:5px;margin-right:5px;background-color:#72b1df">
      {% for pair in row %}
        <th style="padding:5px;">{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}

    {% tablerow pair in row %}
      <span style="background-color:#f6f6f6">{{ pair[1] }}</span>
    {% endtablerow %}
  {% endfor %}
</table>

<style>
  td{
    padding:5px;
    border:1px solid lightgray;
  }
  table tbody{
    display: block;
    max-width:700px;
    overflow-x:scroll;
  }
  table{
    border-radius: 15px;
    margin:auto
  }
</style>


<hr>

Contact us for more information about what fields stands for, and how to use them
