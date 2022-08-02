---
description: Git 명령어 Revert와 Reset에 차이
---

# Revert vs Reset

## 차이점

가장 큰 차이점으로는 **Revert**는 Commit 기록이 그대로 남아있는 것이고, **Reset**은 Commit 기록이 사라진다.

즉, **Revert**는 이전 기록으로 되돌아갈 수 있으면서, 이전에 커밋한 내용도 히스토리에 남아있다. **Reset**은 이전 기록으로 되돌아갈 수 있지만, 이전의 커밋한 내용이 사라져 히스토리에 남아있지 않다.

## Revert 명령어

```bash
git revert <commit>
```

Commit에서 변경한 모든 변경 사항을 되돌려 새로운 커밋으로 생성하고, 현재 브랜치에 적용하는 명령어

## Reset 명령어

```bash
git reset <option> <commit>
```

Commit 기록을 삭제하는데, 변경된 내용을 삭제하거나 남기거나 하는 것을 옵션으로 지정함. 공용 브랜치에서 사용하면 안됨.

### Hard Option

```bash
git reset --hard <commit>
```

돌아가려는 커밋 이후의 모든 이력이 다 사라짐

### Soft Option

```bash
git reset --soft <commit>
```

되돌아 가지만, 변경된 내용은 스테이지에 올라가 있음.

즉, 되돌아가려는 커밋 이후에 한 커밋 내용이 스테이지에 남아있게 할 때??

### Mixed Option (Default)

```
git reset --mixed <commit>
```

되돌아 가지만, 변경된 내용은 스테이지에 올라가있지 않음.

### 현재에서 몇 개 이전 이력으로 돌아가려고 할 때

```bash
git reset HEAD~5 // 현재에서 5개 이전으로 돌아갈 때
```

## 그림

![Revert vs Reset](<../.gitbook/assets/image (2).png>)

## 언제 사용?

* _**Revert**_ : 중간에 잘못된 커밋만 없앨 경우
* _**Reset**_ : _****_ 다 잘못되면&#x20;

## Reference

1. [https://victorydntmd.tistory.com/79](https://victorydntmd.tistory.com/79)
2. [https://medium.com/nonamedeveloper/초보용-git-되돌리기-reset-revert-d572b4cb0bd5](https://medium.com/nonamedeveloper/%EC%B4%88%EB%B3%B4%EC%9A%A9-git-%EB%90%98%EB%8F%8C%EB%A6%AC%EA%B8%B0-reset-revert-d572b4cb0bd5)
3. [http://www.devkuma.com/books/pages/434](http://www.devkuma.com/books/pages/434)
