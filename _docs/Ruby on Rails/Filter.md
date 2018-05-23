---
title: Filter
permalink: /docs/Filter/
comments: true
---
#### 필터는 액션의 <b>직전</b>, <b>직후</b> 혹은 <b>둘 다</b>에 실행되는 메소드
필터는 상속이 가능하여, ApplicationController에 필터를 설정하면 모든 컨트롤러에 적용
<br/>

* <h4>before</h4>
액션이 실행되기 직전에 실행<br/>
아래는 사용자가 액션을 실행하기 전에 로그인을 요구하는 것
{% highlight ruby %}
class ApplicationController < ActionController::Base
  # devise gem 사용 시
  # before_action :authenticate_user!
  before_action :require_login

  private

  def require_login
    unless user_signed_in?
      redirect_to 'users/sign_in'
    end
  end
end
{% endhighlight %}

* <h4>after</h4>
액션이 실행된 후에 실행<br/>
<b>클라이언트에 전송할 데이터에 접근할 수 있다</b><br/>
어떻게 작성하여도 액션의 실행을 중단할 수 없다
<br/>

* <h4>around</h4>
필터 내부의 어딘가에서 반드시 yield를 실행해서 액션을 실행해야한다<br/>
화면 출력(랜더링)도 yield에 포함된다<br/>
일부러 yield를 실행하지 않고 직접 응답을 생성한다는 방법도 존재, 이 경우 액션은 실행되지 않는다
<hr/>

#### 필터가 적용되는 액션을 지정하는 방법
* <h4>only</h4>
only는 특정 액션에만 필터를 적용한다
{% highlight ruby %}
class PostController < ApplicationController
  # devise gem 사용 시
  # before_action :authenticate_user!, only:[:show, :create]
  before_action :require_login, only: [:show, :create]
end
{% endhighlight %}

* <h4>except</h4>
except는 특정 액션을 제외하고 필터를 적용한다
{% highlight ruby %}
class PostController < ApplicationController
  # devise gem 사용 시
  # before_action :authenticate_user!, except: :index
  before_action :require_login, except: :index
end
{% endhighlight %}

* <h4>skip_before_action</h4>
ApplicationController에 필터를 적용했을 시, skip_before_action을 사용하여 특정 액션에서 필터를 적용하지 않을 수 있다
{% highlight ruby %}
class PostController < ApplicationController
  # devise gem 사용 시
  # skip_before_action :authenticate_user!, only:[:show, :create]
  skip_before_action :require_login, only: [:new, :create]
end
{% endhighlight %}
skip_before_action ~, only: ~의 경우 특정 액션을 제외하고 필터를 적용하게 된다
