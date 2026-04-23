# mowkow
머꼬: 한글 LISP

## 실행 방법

1. github에서 해당 소스코드를 다운로드 하거나 clone 하세요.
2. Python >= 3.10 이 설치되어 있는지 확인하세요. 

```bash
$ python3 --version
Python 3.10.11
```

3. 이후 아래에서 자신의 운영체제에 맞는 명령어를 수행하세요.

### 윈도우 사용자

```bash
$ cd mowkow
$ python -m venv venv
$ .\venv\Scripts\activate
$ pip install -e .

Obtaining file:///C:/mowkow
  Installing build dependencies ... done
  Checking if build backend supports build_editable ... done
  Getting requirements to build editable ... done
  Preparing editable metadata (pyproject.toml) ... done
Building wheels for collected packages: mowkow
  Building editable for mowkow (pyproject.toml) ... done
  Created wheel for mowkow: filename=mowkow-1.0.0-0.editable-py3-none-any.whl size=4085 sha256=01530d76c5c744e58588bf4a7dea031e55d56053c394e133039f6d8220eb44b0
  Stored in directory: C:\Users\sigma\AppData\Local\Temp\pip-ephem-wheel-cache-u094awio\wheels\cb\aa\c3\598f368e431effd05415741958adbc489c12b4ebde3be07bd4
Successfully built mowkow
Installing collected packages: mowkow
Successfully installed mowkow-1.0.0

[notice] A new release of pip is available: 23.0.1 -> 26.0.1
[notice] To update, run: python.exe -m pip install --upgrade pip

$ mk
```

### 맥/리눅스 사용자

```bash
$ cd mowkow
$ python3 -m venv venv
$ source venv/bin/activate
$ pip install -e .

Obtaining file:///D:/mowkow
  Installing build dependencies ... done
  Checking if build backend supports build_editable ... done
  Getting requirements to build editable ... done
  Preparing editable metadata (pyproject.toml) ... done
Building wheels for collected packages: mowkow
  Building editable for mowkow (pyproject.toml) ... done
  Created wheel for mowkow: filename=mowkow-1.0.0-0.editable-py3-none-any.whl size=4085 sha256=01530d76c5c744e58588bf4a7dea031e55d56053c394e133039f6d8220eb44b0
  Stored in directory: C:\Users\sigma\AppData\Local\Temp\pip-ephem-wheel-cache-u094awio\wheels\cb\aa\c3\598f368e431effd05415741958adbc489c12b4ebde3be07bd4
Successfully built mowkow
Installing collected packages: mowkow
Successfully installed mowkow-1.0.0

[notice] A new release of pip is available: 23.0.1 -> 26.0.1
[notice] To update, run: python.exe -m pip install --upgrade pip

$ mk
```

종료하려면 그냥 엔터를 입력하면 됩니다.

## 테스트 입력

다음 입력을 수행해 보세요.

```
>  (+ 10 20)
30
>  (그대로 10)
10
>  (그대로 (+ 10 20))
30
>  (그대로 '(+ 10 20))
(+ 10 20)
>  (절댓값 (- 20))
오류: <내장함수 '-'>: 인수 개수 오류입니다.
>  (절댓값 (- 0 20))
20
>  (머 '(1 2 3))
1
>  (꼬 '(1 2 3))
(2 3)
>  (잠시 ((이 2) (삼 3)) (+ 이 삼))
5
>  (정의 (합 수) (만약 (= 수 0) 0 (+ 수 (합 (- 수 1)))))
>  (합 4)
10
>  (정의 합 (람다 (수) (만약 (= 수 0) 0 (+ 수 (합 (- 수 1))))))
>  (합 5)
15
>  (잠시 ((인수 5) (합 (람다 (수) (만약 (= 수 0) 0 (+ 수 (합 (- 수 1))))))) (합 인수))
15
```

## 테스트 프로그램

다음은 두 양수를 입력받아 최대공약수와 최소공배수를 구하는 프로그램(`gcd_lcm.mk`)입니다.

```
(정의 (나머지 가 나)
      (- 가 (* (/ 가 나) 나)))

(정의 (최대공약수 가 나)
      (만약 (= 나 0)
            가
            (최대공약수 나 (나머지 가 나))))

(정의 (최소공배수 가 나)
      (/ (* 가 나) (최대공약수 가 나)))

(정의 가 (읽기))
(정의 나 (읽기))
(쓰기 (최대공약수 가 나))
(쓰기 (최소공배수 가 나))
```

위 프로그램은 다음과 같이 수행할 수 있습니다.

```
$ mk test_code\gcd_lcm.mk
12 # 엔터
6  # 엔터
6
12
```

## 테스트 코드

테스트 코드 폴더의 테스트 파일 source.mk를 수행하려면 다음과 같이 수행하시면 됩니다.

```
$ mk test_code/source.mk
```

## Authors

* **우균(Gyun Woo)** - *최초 작업* - [Gyun Woo](https://github.com/woogyun)


