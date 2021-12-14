내 깃허브 <https://github.com/zabd0ng> 에 jekyll 블로그를 위한 원격 repository를 생성  
원격 repository의 이름은 _"zabd0ng.github.io"_ 로 설정(github에서 jekyll 블로그를 호스팅하기 위해)  
바탕화면에 작업을 할 디렉토리(bloggame\blog)를 생성해주고 git clone 명령어로 내 원격 repository를 불러왔다.  
테마를 골랐는데, _"Pixyll"_ 이라는 테마가 단순하고 직관적인 것 같아서 고르게 되었다. <https://github.com/johno/pixyll> 에서 zip으로 파일들을 다운받은 후 압축을 풀고 원래 있던 "_post" 디렉토리를 제외하고 작업 디렉토리인 blog 디렉토리에 붙여넣기했다.  
처음 테마를 jekyll에서 적용시키는데 애를 먹었는데,  
```bundle exec jekyll serve```를 터미널에 입력했지만 오류가 발생했다.  
수업 시간에 배운 순서대로 모든 걸 진행한 것 같았지만 계속 서버가 열리지 않았다.  
gemfile에 해당 테마에서 사용하는 gem 플러그인(?)이 필요했고 여러 조사 끝에 해답을 찾을 수 있었다.  
```bundle update```로 gemfile 내의 gem들을 업데이트 하고 ```bundle install```로 gem들을 설치하는 작업을 해야 jekyll 블로그가 오류없이 실행이 됐다.  
markdown 문법을 간단하게 실습해보기 위해 post에 _"2021-12-14-hiphop.md"_ 를 작성해봤다. url 삽입과 글씨 크기, 개행 등을 연습해봤다. 