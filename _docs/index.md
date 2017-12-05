---
title: Hello World
permalink: /docs/home/
redirect_from: /docs/index.html
---

#### You can choose category to read docs
<br/>
C
{% highlight c %}
   printf("Hello World");
{% endhighlight %}

C#
{% highlight c# %}
   Console.WriteLine("Hello World");
{% endhighlight %}

Python
{% highlight python %}
   print("Hello World")
{% endhighlight %}

Ruby
{% highlight ruby %}
   puts("Hello World")
{% endhighlight %}

<hr/>
##### Recent docs


<ul class="list-group">
    {% for post in site.docs limit:10 %}
    <li class="list-group-item">
    <a href="{{ post.url | prepend: site.baseurl }}" {% if page.title==post.title %} class="list-group-item active" {% endif %}>
    {{ post.title }}</a>
    </li>
    {% endfor %}
</ul>
