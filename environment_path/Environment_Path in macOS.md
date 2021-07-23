# Environment_Path in macOS

### Anaconda 환경변수 설정

***"zsh: conda not found error: conda"***

아나콘다를 설치하고 위와 같은 error가 일어날 경우 환경 변수를 잡아줘야 한다

만약 기존의 zsh에서 anaconda를 사용하고 있더라도 oh-my-zsh를 설치한다면 환경 변수를 다시 잡아줘야 한다

***conda init*** : conda의 초기 설정을 변경해주는 명령어

```bash
# zsh(혹은 사용하고자 하는 shell 환경) 
conda init zsh
```

conda init zsh을 실행하고 ~/.zshrc에 들어가 보면 아래와 같은 내용이 추가된 것을 확인할 수 있다.

conda init을 실행하지 않고 해당 내용을 ~/.bash_profile에서 복사하여 ~/.zshrc에 추가해 줘도 상관없음

![Environment_Path%20in%20macOS%20055fcfd2935c42339eb239bd54a41982/Screen_Shot_2021-07-23_at_11.43.16_AM.png](Environment_Path%20in%20macOS%20055fcfd2935c42339eb239bd54a41982/Screen_Shot_2021-07-23_at_11.43.16_AM.png)

default가 zsh이라면 터미널/iterm2를 실행시켰을 때 자동으로 conda가 활성화된다.