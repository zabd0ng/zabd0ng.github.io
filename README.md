# jekyll을 이용한 나만의 블로그 만들기

## 1. 원격 repository 생성 및 jekyll 설치  
내 깃허브 <https://github.com/zabd0ng> 에 jekyll 블로그를 위한 원격 repository를 생성  
원격 repository의 이름은 _"zabd0ng.github.io"_ 로 설정(github에서 jekyll 블로그를 호스팅하기 위해)  
다음으로 ruby + devkit을 설치해주었다.  
```gem install jekyll bundler``` 로 jekyll을 설치해 사전 준비를 마쳤다.  
  
## 2. 테마 적용  
바탕화면에 작업을 할 디렉토리(bloggame\blog)를 생성해주고 git clone 명령어로 내 원격 repository를 불러왔다.  
테마를 골랐는데, _"Pixyll"_ 이라는 테마가 단순하고 직관적인 것 같아서 고르게 되었다. <https://github.com/johno/pixyll> 에서 zip으로 파일들을 다운받은 후 압축을 풀고 원래 있던 "_post" 디렉토리를 제외하고 작업 디렉토리인 blog 디렉토리에 붙여넣기했다.  
처음 테마를 jekyll에서 적용시키는데 애를 먹었는데,  
```bundle exec jekyll serve```를 터미널에 입력했지만 오류가 발생했다.  
수업 시간에 배운 순서대로 모든 걸 진행한 것 같았지만 계속 서버가 열리지 않았다.  
gemfile에 해당 테마에서 사용하는 gem 플러그인(?)이 필요했고 여러 조사 끝에 해답을 찾을 수 있었다.  
```bundle update```로 gemfile 내의 gem들을 업데이트 하고 ```bundle install```로 gem들을 설치하는 작업을 해야 jekyll 블로그가 오류없이 실행이 됐다.  
  
## 3. markdown 문법을 이용해 내 블로그에 post 작성하기  
markdown 문법을 간단하게 실습해보기 위해 post에 _"2021-12-14-hiphop.md"_ 를 작성해봤다. url 삽입과 글씨 크기, 개행 등을 연습해봤다.  
필수 과제 중 하나인 post 작성하기로 git의 역사와 간단한 명령어들에 관련된 post, _"2021-12-15-history of git"_를 작성했다.  
제목태그"#"와 표||를 이용했고 ```코드블록```도 사용했다.  
  
## 4. disqus 댓글창 적용  
disqus 회원가입 후 universal code를 post.html에 붙여넣고 테마에 맞게 수정하였다.  
  
```
{% if page.comments %}
<h2>Comments</h2>
<div id="disqus_thread"></div>
<script>
    /**
    *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
    *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables    */
    let PAGE_URL = "{{site.url}}{{page.url}}"
    let PAGE_IDENTIFIER = "{{page.url}}"
    var disqus_config = function () {
    this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
    this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
    };
    
    (function() { // DON'T EDIT BELOW THIS LINE
    var d = document, s = d.createElement('script');
    s.src = 'https://yunmin-blog.disqus.com/embed.js';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
{% endif %}
```  
작성한 포스트에 ```comments: true``` 를 넣어 해당 post에서만 댓글 작성이 가능하게 했다.  
  
## 5. favicon 만들기  
favicon 생성을 위해 <https://www.favicon-generator.org/> 에서 내가 그린(?) 그림으로 favicon을 만들었다.  
사이트에서 생성된 코드를 "_include"폴더의 head.html에 붙여넣어주었다.  
밑은 해당 코드이다.  
```
    <link rel="apple-touch-icon" sizes="57x57" href="/apple-icon-57x57.png">
    <link rel="apple-touch-icon" sizes="60x60" href="/apple-icon-60x60.png">
    <link rel="apple-touch-icon" sizes="72x72" href="/apple-icon-72x72.png">
    <link rel="apple-touch-icon" sizes="76x76" href="/apple-icon-76x76.png">
    <link rel="apple-touch-icon" sizes="114x114" href="/apple-icon-114x114.png">
    <link rel="apple-touch-icon" sizes="120x120" href="/apple-icon-120x120.png">
    <link rel="apple-touch-icon" sizes="144x144" href="/apple-icon-144x144.png">
    <link rel="apple-touch-icon" sizes="152x152" href="/apple-icon-152x152.png">
    <link rel="apple-touch-icon" sizes="180x180" href="/apple-icon-180x180.png">
    <link rel="icon" type="image/png" sizes="192x192"  href="/android-icon-192x192.png">
    <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
    <link rel="icon" type="image/png" sizes="96x96" href="/favicon-96x96.png">
    <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
    <link rel="manifest" href="/manifest.json">
    <meta name="msapplication-TileColor" content="#ffffff">
    <meta name="msapplication-TileImage" content="/ms-icon-144x144.png">
    <meta name="theme-color" content="#ffffff">
```