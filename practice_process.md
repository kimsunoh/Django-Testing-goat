# 전제조건 및 가정
```
pip3 install django==1.11
pip3 install install --upgrade selenium
```

# django project 생성
- functional_test.py 작성 후 테스트
```
from selenium import webdriver

browser = webdriver.Chrome('chromedriver')
browser.get('http://localhost:8000')

assert 'Django' in browser.title
# 오류 내용을 확인
```
	- selenium에서 브라우저를 사용하려면 브라우저 드라이버를 설치해야한다
- 프로젝트 생성
```bash
$ django-admin.py startproject superlists
$ cd superlists
```
- django manage test
```bash
$ python manage.py test
```

## browser driver 설치
```
brew install geckodriver
```

# django project git 적용
- funtional_test.py 를 superlists로 이동
```bash
$ mv functional_test.py superlists
```
- git 레포지터리 생성
```bash
$ cd superlists
$ git init
$ vi .gitignore
> ### Django ###
> __pycache__/
> db.sqlite3
$ git 
```

# 단위 테스트를 이용한 간단한 홈페이지 테스트
- django app을 추가한다
```bash
$ python3 manage.py startapp lists
```
- lists를 git에 add 후 커밋한다
- lists에 HomePageTest 클래스를 추가하고 테스트를 하며 수정하자
- `funcional_test.py`의 시나리오에 맞는 `HomePage` 테스트를 `lists/test.py` 에 추가한다

# 왜 테스트를 하는 것인가?
- 프로그래밍은 우물에서 물을 퍼 올리는 것과 같다
	- TDD는 훈련이므로 이렇게 연습의 과정을 거쳐야 자연스럽게 할 수 있게 된다

# homepage 기능 테스트 수정
- 상세 기능 테스트 내용을 'functional_test.py'에 추가
- 'HomePage'부분의 테스트를 수정후 home.html 내용 수정
- 상세한 test error msg를 보기위해 `functional_test.py`에 message추가
