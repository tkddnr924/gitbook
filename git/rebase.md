# Rebase

## Merge & Rebase

git에서 다른 브랜치를 합치는 방법은 **Merge**, **Rebase**가 있다.

`git merge`는 서로 다른 브랜치 (a, b)를 병합할 때 아래 코드처럼 실행한다. 이렇게 하면 a 브랜치 뒤에 하나의 커밋을 생성하여 병합한다.

```
git checkout a
git merge b
```

git rebase는 서로 다른 브랜치(a, b)를 병합할 때, 아래 코드처럼 실행한다. 이렇게 하면 a 브랜치 뒤에 b의 커밋이 추가된다.

```
git checkout b
git rebase a
```

## Rebase 그림 예시

![Rebase Example](<../.gitbook/assets/image (1).png>)

## Reference

1. [https://suhwan.dev/2018/01/21/Git-Rebase-1/](https://suhwan.dev/2018/01/21/Git-Rebase-1/)

