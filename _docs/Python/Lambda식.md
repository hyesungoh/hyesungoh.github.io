---
title: Lambda식
permalink: /docs/Lambda식/
comments: true
---
#### 기본 형식
{% highlight python %}
   # lambda 인자: 식
   print((lambda x: x + 10)(20))
   # prints 30
{% endhighlight %}
<br>
#### 함수로 표현하면?
{% highlight python %}
  def plusTen(x):
    return x + 10

  print(plusTen(20))
  # prints 30
{% endhighlight %}
<br>
#### Map, Filter 함수와 유용하게 사용됨
