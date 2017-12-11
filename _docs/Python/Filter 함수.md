---
title: Filter 함수
permalink: /docs/Filter 함수/
comments: true
---
#### 기본 형식
{% highlight python %}
   list(filter(func, iterable))
   # filter(함수, 반복가능한 자료형)
{% endhighlight %}

<br>

* <h5> 각 요소 모두 함수에 적용시킨 후 값이 참인 것들을 반환 </h5>
{% highlight python %}
  def overTen(x):
    return x > 10

  l = [11, 2, 3, 14]
  otl = list(filter(overTen, l))
  print(otl)
  # prints [11, 14]
{% endhighlight %}

<br>

#### <a href="https://hyesungoh.github.io/docs/Lambda%EC%8B%9D/" target="blank">Lambda식</a>과 유용하게 사용됨
{% highlight python %}
  l = [11, 2, 3, 14]
  otl = list(filter(lambda x: x > 10, l))

  print(otl)
  # prints [11, 14]
{% endhighlight %}

<br>

#### 예
{% highlight python %}
  l = [1, 2, 3, 4, 5]
  m = list(filter(lambda x: x % 2 == 0, l))

  print(m)
  # prints [2, 4]
{% endhighlight %}
