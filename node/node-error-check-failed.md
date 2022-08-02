---
description: 'Error: Check failed: allocator->SetPermissions'
---

# \[Node Error] Check failed

## ISSUE

Mac OS, M1 칩에서 Node 사용 시 발생하는 에러.

{% hint style="danger" %}
Fatal error in , line 0

Check failed: allocator->SetPermissions(reinterpret\_cast(region.begin()), region.size(), PageAllocator::kNoAccess).
{% endhint %}

## Solution

Node Version은 15.9.0 이상으로 업그레이드 해야함

```
arch -arm64 brew upgrade node
```

## Refference

* [https://velog.io/@maliethy/wasm-code-commit-Allocation-failed-process-out-of-memory](https://velog.io/@maliethy/wasm-code-commit-Allocation-failed-process-out-of-memory)
