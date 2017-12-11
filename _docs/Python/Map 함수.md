---
title: Map 함수
permalink: /docs/Map 함수/
comments: true
---
#### 기본 형식
{% highlight python %}
   list(map(func, iterable))
   # map(함수, 반복가능한 자료형)
{% endhighlight %}

<br>

* <h5> 각 요소 모두 함수에 적용된 값들을 반환 </h5>
{% highlight python %}
  def plusTen(x):
    return x + 10

  l = [1, 2, 3, 4]
  ptl = list(map(plusTen, l))
  print(ptl)
  # prints [11, 12, 13, 14]
{% endhighlight %}
* <h6> Python 2.7은 map 함수의 반환값이 list형 </h6>

<br>

#### Lambda식과 유용하게 사용됨
{% highlight python %}
  l = [1, 2, 3, 4]
  ptl = list(map(lambda x: x + 10, l))

  print(ptl)
  # prints [11, 12, 13, 14]
{% endhighlight %}

<br>

#### 예
{% highlight python %}
  n = 12345
  l = list(map(int, str(n)))

  print(l)
  # prints [1, 2, 3, 4, 5]
{% endhighlight %}
