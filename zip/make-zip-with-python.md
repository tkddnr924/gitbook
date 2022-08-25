---
description: 파이썬으로 zip 파일 만들기
---

# MAKE ZIP with PYTHON

## 모듈

1. `zipfile`
2. **`pyminizip`**

### 사용

pyminizip

## zipfile

### 단점

* password 설정 못함 :cry:

### 사용

```python
from zipfile import ZipFile, ZIP_DEFLATED

def compress():
    with ZipFile('compress_your_file.zip', 'w', allowZip64=True) as zipper:
        for (path, dir, files) in os.walk('compress_your_path'):
            for file in files:
                # write
                zipper.write(os.path.join(path, file), compress_type=ZIP_DEFLATED)
        zipper.close()
    return
```

## pyminizip

### 단점

* Documentation이 잘 정리 안되어있음 (빈약함)
* 모듈 설치 필요

### 설치

`pip install pyminizip`

### 사용

<pre class="language-python"><code class="lang-python">import pyminizip

def compress():
<strong>    compress_list = []
</strong>    path_list = []
    
    for (path, dir, files) in os.walk('your_path'):
        for file in files:
            path_list.append(path)
            target = os.path.join(path, file)
            compress_list.append(target)
    
    # write
    pyminizip.compress_multiple(
        compress_list,    # 파일 리스트
        path_list,        # 파일 prefix (= 경로) 주의사항. 파일 리스트와 길이가 같아야함! 
        'compress_your_file.zip',    # 압축 파일 명
        'your_password',  # 패스워드
        5,                # 압축률 / type:int / ( 1 ~ 9 ) / 1: 빠름 9: 압축률 높음
        progress          # 압축할 때 호출될 함수. 파라미터는 1개(count: 몇 번째인지). 총 개수는 없음
    )
    return
    
def progress(count):
    print(count)
</code></pre>
