---
title: Terminal - time set
permalink: /docs/Terminal-time-set/
comments: true
---
#### 시간 확인 방법
{% highlight bash %}
$ date "+%H:%M:%S   %d/%m/%y"

=> 15:02:55   03/06/18
{% endhighlight %}
<br/>

#### 시간 설정 방법
{% highlight bash %}
$ sudo dpkg-reconfigure tzdata

=> Current default time zone: 'Asia/Seoul'
=> Local time is now:      Mon Jun  4 00:04:59 KST 2018.
=> Universal Time is now:  Sun Jun  3 15:04:59 UTC 2018.
{% endhighlight %}
<br/>
