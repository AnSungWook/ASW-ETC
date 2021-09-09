# Git - prepare-commit-msg

- Git hook 에는 여러가지 기능들이 있음
- 그 중 커밋전에 메시지를 커스텀 할 수 있게끔 하는 기능이 있음 prepare-commit-msg 임

## 사용법

- 해당 프로젝트의 폴더로 이동 
- .git > hooks 로 이동 
- **가끔 hooks 폴더가 없을 경우가 있으니 직접 만들어도 됨**
- .git/hooks/prepare-commit-msg 를 작성 
- *예시 ( 자동으로 브랜치명 붙이기 )*
```shellscript
#!/bin/sh
#
# Automatically adds branch name and branch description to every commit message.
#
NAME=$(git branch | grep '*' | sed 's/* //' | sed 's/feature\///')
DESCRIPTION=$(git config branch."$NAME".description)

echo "[$NAME]" | cat - "$1" > /tmp/out && mv /tmp/out "$1"
if [ -n "$DESCRIPTION" ]
then
   echo "" >> "$1"
   echo $DESCRIPTION >> "$1"
fi
```

> git hooks 에는 다양한 기능들이 존재 하니 상황에 맞춰 사용하면 좋을거 같다.