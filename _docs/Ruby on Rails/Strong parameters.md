---
title: Strong parameters
permalink: /docs/Strong parameters/
comments: true
---
#### 대량 할당 - Mass Assignment
레일즈는 파라미터를 이용하여 모델 객체를 생성 가능
{% highlight ruby %}
class PostController < ApplicationController
  def create
    Post.create(params)
  end
end
{% endhighlight %}
<br/>

#### 문제점
사용자가 예상치 못한 HTTP 요청 파라미터를 전달했을 때 발생
{% highlight ruby %}
  { id: 1, name: 'hyesung', pwd: 'password', is_admin: true }
  # 위와 같이 회원이 관리자로 지정될 가능성이 존재
{% endhighlight %}
<br/>

<h4> 해결방법 - <a href="https://github.com/rails/strong_parameters">Strong parameters</a></h4>
{% highlight ruby %}
  # in Gemfile
  gem 'strong_parameters'
{% endhighlight %}

* <h5>permit</h5>
{% highlight ruby %}
class PostController < ApplicationController
  def create
    post = Post.create(post_params)
    post.save
  end

  private
    def post_params
      params.permit(:title, :content, :hashtags)
    end

end
{% endhighlight %}
<p>위 예제는 permit을 사용하여 whitelist(title, content, hashtag)에 해당하는 값만 허용</p>
<p>whitelist에 없는 값이 존재 시 경고 로그를 남기고 whitelist에 해당하는 값만 반환</p>

* <h5>require</h5>
{% highlight ruby %}
class PostController < ApplicationController
  def create
    post = Post.create(post_params)
    post.save
  end

  private
    def post_params
      params.require(:title).permit(:content, :hashtags)
    end

end
{% endhighlight %}
<p>위 예제는 require를 사용하여 필수적으로 포함 할 값을 지정한 것</p>
<p>require 값이 없을 시 ParameterMissing 예외 발생</p>

  * <h5>다중 require</h5>
  {% highlight ruby %}
  class PostController < ApplicationController
    def create
      post = Post.create(post_params)
      post.save
    end

    private
      def post_params
        params.require(:time)
        params.require(:age)
        params.require(:title).permit(:content, :hashtags)
      end

  end
  {% endhighlight %}
