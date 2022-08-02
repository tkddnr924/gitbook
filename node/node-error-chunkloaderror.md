---
description: 'ChunkLoadError: Loading chunk 3 failed'
---

# \[Node Error] ChunkLoadError

## ISSUE

Chunk 파일 로딩 에러 (Next.js 하다가 발견)

{% hint style="danger" %}
https://cpsp.kr/players/ (v 1.0.2)\
ChunkLoadError: Loading chunk 3 failed.\
(error: https://cpsp.kr/static/js/3.62522664.chunk.js)\
Loading chunk 3 failed.\
(error: https://cpsp.kr/static/js/3.62522664.chunk.js)
{% endhint %}

## Solution

.next 폴더를 삭제 후 재빌드!

```
rm -rf .next
yarn build
```

## Reference

* [https://satisfactoryplace.tistory.com/194](https://satisfactoryplace.tistory.com/194)
