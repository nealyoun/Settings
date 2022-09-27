# Mac - iTerm2 setting

### 설치 및 설정하기 앞서 iTerm2의 기본적인 단축키

- iTerm2 shortcuts
    - 새창: command + n
    - 새 탭: command + t
    - 탭 이동: command + 방향키, command + 번호
    - 탭 세로 분할: command + d
    - 탭 가로 분할: command + shift + d
    - 탭 투명하게 설정: command + i
    - 탭 투명하게: on/off : command + u
    - 탭 닫기: command + w
    - 탭 분할 시 포커스 찾기: command + /
    - 탭 분할 포커스 이동: command + [ , ]
    - 전체 검색: command + option + e
    - 검색: command + F
    - 클립보드: command + Shift + H
    - 자동완성: command + ;, 방향키(→)
    - 작업시간 보여주기: command + shift + e
    - 터미널 명령어 한번에 삭제: ctrl + u
---
### iTerm2는 macOS의 third party 앱으로 기존의 터미널 앱보다 확장된 기능을 제공한다. 맥의 터미널도 이미 훌륭하고 사용하는데 불편함은 없지만, 다양한 커스터마이징을 지원하고 zsh을 사용하기 때문에 bash에 비해 편리한 부분이 많다.<br> (설치 하면서 알게 되었지만 Oh-My-Zsh를 이용하여 다양한 plugin을 설치해도 terminal에서 다양한 기능을 충분히 활용할 수 있음)

### 1. iTerm2 & zsh + Oh-My-Zsh 설치

iTerm 혹은 zsh 둘중 어느 것을 먼저 설치하더라도 상관없다. 하지만 oh-my-zsh는 zsh의 확장판과 같은 개념이기 때문에 zsh가 설치된 환경에서 추가적으로 설치해야한다. (MacOS Catalina 부터는 default로 zsh가 설치되어 있기 때문에 oh-my-zsh만 설치 하면 된다. )

#### 1. Homebrew 를 이용하여 설치

[Homebrew](https://brew.sh/index_ko) 를 이용하고 있다면 아래의 코드를 terminal에 입력하여 설치
```bash
# iterm2 설치
brew install --cask iterm2
```

#### 2. iTerm2는 [여기](https://iterm2.com/)에서 다운받아 설치 하면 된다.

![iterm_pre](https://user-images.githubusercontent.com/54128055/192507339-6f1ecf41-761f-4c81-9034-2759e6c6363f.png)

![iterm_pre2](https://user-images.githubusercontent.com/54128055/192507332-e1ef2342-21f3-4c45-a8b9-353515892bc8.png)

아래에서 원하는 정보를 표시하도록 커스텀 할 수 있음
![iterm_pre3](https://user-images.githubusercontent.com/54128055/192506833-acd9d196-7738-43f6-8597-de079d314dec.png)

---

### 2. Oh-My-Zsh 설치

<img width="480" alt="Screen_Shot_2021-07-22_at_12 57 16_AM" src="https://user-images.githubusercontent.com/54128055/126535900-24550dfa-339a-4cbf-8f6c-9645052510a4.png">
echo$ 0 를 통해 현재 자신의 default shell를 확인 할 수 있음

zsh는 brew를 통해 손쉽게 설치 가능

```bash
# install zsh
brew install zsh

# oh-my-zsh install
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
---

### 3. Color Theme 적용

#### agnoster

해당 [링크](https://github.com/mbadolato/iTerm2-Color-Schemes)를 통해 원하는 색상의 테마를 선택하여 적용 할 수 있다.

위의 iTerm color는 [oceanic-next-iterm](https://github.com/mhartington/oceanic-next-iterm/archive/refs/heads/master.zip) 이다.

master.zip을 다운받은 후 Oceanic-Next.itermcolors 파일을 실행하여 테마를 추가 해줘야한다. 

iterm2 → preferences → profiles → colors → 오른쪽 하단의 color presets 에서 다운 받은 color theme 을 선택

![Screen_Shot_2021-07-22_at_1 13 31_AM](https://user-images.githubusercontent.com/54128055/126535874-875a4b61-5680-43c4-b0c7-3321b08b700e.png)
#### iTerm/Terminal theme 적용

terminal 혹은 iterm을 실행시켜 아래의 명령어 중 편한 것을 선택하여 입력

<img width="480" alt="Screen_Shot_2021-07-22_at_1 17 06_AM" src="https://user-images.githubusercontent.com/54128055/126535881-6d3fd312-fe9e-4bfb-a100-e5c3c9beb967.png">

<img width="480" alt="Screen_Shot_2021-07-22_at_1 17 42_AM" src="https://user-images.githubusercontent.com/54128055/126535885-7b0274ea-2c88-4207-b8dd-4b450ef81c5a.png">

ZSH_THEME = "robbyrussell" 인 부분을 찾아

ZSH_THEME = "agnoster" 로 수정해준다

![Screen_Shot_2021-07-22_at_1 19 32_AM](https://user-images.githubusercontent.com/54128055/126535886-958ea2f7-9d78-46ea-83fd-758346d3ac34.png)

만약 위 처럼 **vi ~/.zshrc** 로 진입시 "i" 를 눌러 해당부분을 수정하고, 수정 한 후 esc를 눌르고 ":wq"를 입력하고 실행시켜주면 저장된다

> agnoster theme은 현재 directory에서 Git의 상태가 표시됩니다. 해당 기능은 현재 마스터 브랜치인지 개발 브랜치인지 혹은 커밋을 까먹고 하지 않았는지를 알려줍니다.

#### Font 적용

agnoster 테마로 변경하게 되면 폰트가 깨져서 이상하게 보인다. 이를 해결하기 위해 새로운 폰트를 적용시킨다.

Naver의 [D2coding](https://github.com/naver/d2codingfont/releases/tag/VER1.3.2) 을 많이 추천 하길래 해당 링크를 통해 zip파일을 다운받고 적용시켰다.

<img width="554" alt="Screen_Shot_2021-07-22_at_1 29 50_AM" src="https://user-images.githubusercontent.com/54128055/126535888-8b70188d-a103-4a3c-9c04-b9762255de8b.png">

spotlight 나 alfred를 이용하여 Font Book을 실행하고 

![Screen_Shot_2021-07-22_at_1 30 57_AM](https://user-images.githubusercontent.com/54128055/126536987-4c2b23cf-2095-459f-a8fa-7c3fe657778d.png)
다운받았던 폰트를 추가해주면 Mac에서 해당 font를 사용할 수 있다.

iterm2 → preferences → profiles → text → 하단의 font 에서 다운 받은 서체를 선택한다

![Screen_Shot_2021-07-22_at_1 33 00_AM](https://user-images.githubusercontent.com/54128055/126535891-f41ade92-0839-4e3a-b6ef-771d66908884.png)


#### powerlevel10k

또 다른 theme 으로 [powerlevel10k](https://github.com/romkatv/powerlevel10k)가 있다

아래의 코드를 터미널에 입력하여 테마를 다운
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
위에서 theme 을 agnoster 로 변경했던 것 처럼
ZSH_THEME="powerlevel10k/powerlevel10k" 으로 변경한다

이후 iterm2를 완전히 종료하고(cmd+q) 재시작하면

Powerlevel10k configuration wizard 가 실행되고 안내에 따라 원하는 콘솔창으로 만들어가면 된다.
(Powerlevel10k configuration wizard 내에서 font 또한 설치하고 적용하는 단계가 있으므로 agnoster theme 처럼 별도로 font를 설정할 필요는 없음)

powerlevel10k 테마를 적용하면 아래와 같은 콘솔창을 이용할 수 있다
![iterm](https://user-images.githubusercontent.com/54128055/192509468-a09f179a-baab-4168-9676-03a657e0bc29.png)

여기까지 했다면 iTerm2 꾸미기는 기본적으로 끝났다

---

### 4. 추가적인 plugin 설치 및 적용

Oh-my-zsh를 설치하게 되면 다양한 [플러그인](https://github.com/zsh-users)을 사용할 수 있음.

그 중에서 많은 사람들이 사용하는 zsh-syntax-highlighting와 zsh-autosuggestion을 설치 및 적용

### 4-1. zsh-syntax-highlighting

해당 플러그인은 명령어에 highlight를 적용시켜줌으로서 해당 명령어가 올바른지 올바르지 않은지 색상으로 확인이 가능하다.

<img width="200" alt="Screen_Shot_2021-07-22_at_1 58 35_AM" src="https://user-images.githubusercontent.com/54128055/126535896-3dea0ff7-7cfa-4896-ab22-4d1f88b4025a.png"> <img width="200" alt="Screen_Shot_2021-07-22_at_1 59 34_AM" src="https://user-images.githubusercontent.com/54128055/126535898-e4c39563-d0c0-4e64-8142-f53f006e7880.png">


iTerm2에 아래와 같은 명령어 실행

```bash
# homebrew가 설치되어 있는 경우 
brew install zsh-syntax-highlighting

# ~/.zshrc에 들어가서 (open ~/.zshrc 로 txt편집기로 진입해도 ok!)
vi ~/.zshrc

# code 맨 아래에 해당 코드를 입력해주고 ":wq"로 저장하고 나온다
source /usr/local/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
```

### 4-2. zsh-autosuggestions

해당 플러그인은 명령어 자동완성 기능이다. 명령어 입력 도중 회색 글씨로 추천하는 명령어가 보이게 된다. 타이핑 중 → 방향키를 누르면 자동 완성.

```bash
# brew install
brew install zsh-autosuggestions

# ~/.zshrc 에 진입하여
vi ~/.zshrc

# code 맨 아래에 해당 코드를 입력하고 저장해주고 나온다
source /usr/local/share/zsh-autosuggestions/zsh-autosuggestions.zsh
```

### 4-3. homebrew가 설치되어 있지 않다면

ex) git clone 으로 zsh-autosuggestions 설치

```bash
# zsh-autosuggestions 설치
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# zsh-syntax-highlighting 설치
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

위의 코드를 iterm2에서 실행하여 플러그인을 설치하고 ~/.zshrc 로 들어가

![Screen_Shot_2021-07-22_at_2 19 06_AM](https://user-images.githubusercontent.com/54128055/126537727-f186a019-4fde-4c11-971c-c4ba48547adf.png)

위와 같이 "plugins = (git)" 을 찾는다. 설치한 플러그인을 아래와 같이 입력한 후 저장하고 나온다. 

**참고로 homebrew를 이용하여 플러그인을 설치했을 경우 아래와 같이 plugins = () 목록에 설치한 플러그인을 넣는 방법은 적용되지 않는다. brew로 설치시 위의 brew 설치 방식을 따라야함** 
```
plugins=(
		git
    # other plugins...
    zsh-autosuggestions
)
```
보다 자세한 설치 내용은 [자동완성](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md), [highlight](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md) 을 참조
