---
title: n진수
permalink: /docs/n진수/
comments: true
---
#### 2진수
{% highlight python %}
  n = 123

  bn = bin(n)
  # 0b1111011

  int(bn, 2)
  # 123
{% endhighlight %}
<br>
#### 8진수
{% highlight python %}
  n = 123

  on = oct(n)
  # 0173

  int(on, 8)
  # 123
{% endhighlight %}
<br>
#### 16진수
{% highlight python %}
  n = 123

  hn = hex(n)
  # 0x7b

  int(hn, 16)
  # 123
{% endhighlight %}
<br>
#### n진수를 10진수로
{% highlight python %}
  int(number, n)
{% endhighlight %}
