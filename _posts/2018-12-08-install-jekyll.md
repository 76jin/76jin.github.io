---
title: Jekyll 설치
layout: post
comments: true
---

### Jelly 설치 히스토리

```bash
gem install jekyll   # 기본 테마 사용할 경우.
# gem install minimal-mistakes-jekyll # gem 으로 테마를 관리할 경우.
gem install bundler
jekyll new my-awesome-blog
cd my-awesome-blog
jekyll serve # --watch   # http://localhost:4000
```

### apply plugin - jekyll admin
```bash
vi Gemfile
gem 'jekyll-admin', group: :jekyll_plugins
bundle install
bundle exec jekyll serve  # http://localhost:4000/admin 
```

### Tips
* agnoster 테마 적용이 안되는 문제를 해결한 방법.
```bash
# 1. 테마 설정.
vi ~/.zshrc
ZSH_THEME="agnoster"
# 2. iTerm2 폰트 변경
# 2.1 Preference > Profile > Color > Color Preset > Solarized dark
# 2.2 Preference > Profile > Text > Font > "Powerline" 계열의 폰트로 변경.
# 3. 테마 적용 안되면 최신 테마 다운로드 받기.
cd ~/.oh-my-zsh/themes/
curl -o agnoster.zsh-theme https://gist.githubusercontent.com/agnoster/3712874/raw/43cb371f361eecf62e9dac7afc73a1c16edf89c7/agnoster.zsh-theme
```

* zsh 환경 변수가 이상한 경우
  * which zsh --> /bin/zsh
  * echo $SHELL --> /usr/local/bin/zsh
  * 해결방법
```bash
export PATH="/usr/local/bin/:$PATH" 
```

* 유용한 테마 설치
```bash
# zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
echo "source ${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
# zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions
echo "source ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
# autojump
brew install autojump
vi ~/.zshrc
plugins = ( zsh-syntax-highlighting zsh-autosuggestions autojump )
```

### 참고 블로그
* [멋진 터미널 만들기](https://beomi.github.io/2017/07/07/Beautify-ZSH/)
* [oh-my-zsh 테마 이용해 쉘 바꾸고, 유용한 플러그인 사용하기](http://heetop.blogspot.com/2017/10/oh-my-zsh_12.html)
* [Jazz Up Your “ZSH” Terminal In Seven Steps — A Visual Guide](https://medium.freecodecamp.org/jazz-up-your-zsh-terminal-in-seven-steps-a-visual-guide-e81a8fd59a38)
* [Jekyll and LightSail SSL](https://andygrove.io/2018/05/hosting-jekyll-lightsail-lets-encrypt-ssl/)