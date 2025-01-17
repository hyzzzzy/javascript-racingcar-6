# 🏎️ 2주차 자동차 경주

## 1. 게임 로직

### 1.1 게임 시작

- 경주할 N대의 자동차 이름 입력
- 이름 유효성 검사
- 시도할 횟수 입력
- 횟수 유효성 검사

### 1.2. 게임 진행

- 1대마다 랜덤값을 부여
- 랜덤값이 4이상이면 전진
- N대의 결과를 출력
- 시도할 횟수만큼 반복

### 1.3. 게임 종료

- 가장 많이 전진한 자동차 계산
- 우승자 출력

### 1.4. 폴더 구조

```
__tests__
 ┣ ApplicationTest.js
 ┣ CarRaceTest.js
 ┣ CarTest.js
 ┣ InputTest.js
 ┣ StringTest.js
 ┗ UtilTest.js
src
 ┣ domain
 ┃ ┣ Car.js
 ┃ ┗ CarRace.js
 ┣ utils
 ┃ ┣ consoleOperations.js
 ┃ ┣ index.js
 ┃ ┣ numberOperations.js
 ┃ ┗ validation.js
 ┣ App.js
 ┣ constants.js
 ┗ index.js
```

## 2. 구현 기능 목록

- 입력 함수
- 출력 함수
- 입력한 이름 유효성 검사 함수
    - 쉼표(,)를 기준으로 2개 이상의 이름이 작성되었는지?
    - 각 이름이 1이상 5이하의 글자 수를 가졌는지?
    - 중복된 이름이 없는지?
- 입력한 횟수 유효성 검사 함수
    - 숫자로 이루어졌는지?
    - 1이상의 숫자를 입력했는지?
- 랜덤값 부여 함수
    - 0 ~ 9 사이의 랜덤값 지정
- 랜덤값 판별 함수
    - 0 ~ 9 사이의 랜덤값 중 4이상이 나왔는지 판별
- 판정 함수
    - 각 자동차마다 나온 랜덤값에 따라 판정
    - 4이상의 랜덤값이라면 전진횟수 증가
- 출력할 판정 결과 함수
    - `${이름} : -` 형식으로 출력
    - `-` 는 전진한 횟수만큼 출력
    - 마지막 공백 라인 추가
- 우승자 계산 함수
    - 가장 많이 전진한 자동차 이름 계산
- 출력할 우승자 결과 함수
    - 한 명일 경우, `최종 우승자 : ${이름}` 형식으로 출력
    - 여러 명일 경우,  `최종 우승자 : ${이름}, ${이름}` 형식으로 출력

## 3. 테스트 케이스 목록

### 3.1 게임 시작

- 경주할 N대의 자동차 이름 입력 `InputTest`
    - 공백만 있다면 예외 처리되어야 한다.
    - 2개 미만의 이름이 있다면 예외 처리되어야 한다.
    - 1자 미만인 이름이 있다면 예외 처리되어야 한다.
    - 5자 초과인 이름이 있다면 예외 처리되어야 한다.
    - 중복된 이름이 있다면 예외 처리되어야 한다.
- 시도할 횟수 입력 `InputTest`
    - 숫자로만 이루어진 값이 아니라면 예외 처리되어야 한다.
    - 1미만의 숫자로 이루어진 값이면 예외 처리되어야 한다.
    - 자연수가 아니라면 예외 처리되어야 한다.
    - Number.MAX_SAFE_INTEGER보다 큰 값은 예외 처리 되어야 한다.

### 3.2. 게임 진행

- 랜덤값이 4이상이면 전진
    - 4이상이 나오면 true를 반환해야 한다. `UtilTest`
    - forward 메서드가 실행되면 Car 객체의 position이 1 증가해야 한다. `CarTest`
- 시도할 횟수만큼 반복
    - 시도할 횟수가 0 미만이면 false를 반환해야 한다. `CarRaceTest`

### 3.3. 게임 종료

- 가장 많이 전진한 자동차 계산
    - 가장 많이 전진한 우승자 배열을 반환해야 한다. `CarRaceTest`