# CHAPTER 02 암호의 세계

---

## Section 01 암호



### 1. 암호에서 사용하는 이름

`엘리스와 밥(Alice and Bob)` : 일반적으로 엘리스는 메시지를 전송하고 밥이 수신하는 모델에 사용된다.

`이브(Eve)` : 도청자, 소극적인 공격자를 의미한다.

`멜로리(Mallory)` : 악의를 가진 공격자를 의미한다. 메시지를 수정하고 대체하여 이전의 메시지를 재전송하는 능력을 가지고있다.

`트렌트(Trent)` : 신뢰할 수 있는 중재자, 중립적인 위치에 있는 제3자이다.

`빅터(Victor)` : 의도된 거래나 통신이 실제로 발생했다는 것을 검증할 때 등장한다.

### 2. 송신자, 수신자, 도청자

![27729b0c-b5e5-488d-a48c-a668af4327ed](https://github.com/love-1006/TIL/assets/163835194/b14a7c4b-843c-47fd-915f-8c12895b85b2)
`송신자` : 메일을 보내는 측

`수신자`: 메일을 받는 측

`메시지` : 송신된 정보를 총칭

`도청자` : 악의적인 의도를 가지고 메일을 몰래 읽음 → 기밀성 위협

`적극적인 공격자 멜로리` : 메세지를 갈취 후 내용을 수정해서 수신자에게 보냄 → 무결성 위협

* 정보보호 서비스의 종류에는 `가용성(availablilty)`, `기밀성(confidentinality)`, `무결성(integrity)`, 인증, 부인방지, 소유권 등이 있다.

### 3. 암호화와 복호화

암호기술이란, 중간에서 도청자가 암호문을 가로채어 갖게 된다고 하더라도 특정 비밀값을 모른다면 암호문을 평문으로 복호화 할 수 없도록 하는 기술

`평문(Plaintext)` : 암호화하기 전의 메시지

`암호문(Ciphertext)` : 암호화한 후의 메시지

`암호화` : 평문을 암호문으로 변환하는 과정

`복호화` : 암호문을 평문으로 변환하는 과정

### 4. 암호의 기밀성

위와같은 암호기술의 사용은 메일의 내용을 비밀로 유지해 이브로 부터 메일 내용을 보호한다

→ 메일의 기밀성이 유지된다.

### 5. 해독

`암호해독(Cryptanalysis)` : 수신자 이외의 사람이 암호문으로부터 평문을 복원하려고 시도하는 것

암호해독자 : 암호를 해독하는 사람으로, 나쁜의도를 가진자나 암호연구자 등이 있다.

---

## Section 02 암호화와 복호화의 기호 표현

### 1. 암호 시스템의 요소

암호화, 복호화 하는 일련의 과정에 필요한 모든 요소를 합쳐 암호시스템이라한다.

이를 구성하는 요소로는 평문(plaintext), 암호문(ciphertext), 암호 알고리즘(encryption algorithm), 복호 알고리즘(decryption algorithm), 키(key) 가 있다.

### 2. 암호 시스템의 기호 표현

$$
C = E\kappa(P) = E(k,c)
$$

평문 P를 키 K로 암호화(E)하여

암호문 C를 얻는다

$$
P = D\kappa(C) = D(k,c)
$$

암호문 C를 키 K로 복호화(D)하여

평문 P를 얻는다

---

## Section 03 대칭 암호와 공개 키 암호

### 1. 암호 알고리즘

암호화 알고리즘 : 평문을 암호문으로 만드는 절차

복호화 알고리즘 : 암호문을 평문으로 만드는 절자

암호 알고리즘 : 암호화와 복호화 알고리즘을 합한 알고리즘

### 2. 키

암호 알고리즘의 키는 매우 긴 숫자로 이루어져있다.

키는 2진화된 숫자로 변경하여 사용한다. → 2진수로 된 평문에 비밀정보인 2진수로 이루어진 키를 적용하여 2진수로 된 암호문을 만들어내는 과정

### 3. 대칭암호와 비대칭암호

`대칭암호(symmetric crypotography)` : 암호화를 할 때 사용하는 키와 복호화 할 때 사용하는 키가 동일한 암호알고리즘

`비대칭암호(asymmetric cryptography)` : 암호화를 할 때 사용하는 키와 복호화 할 때 사용하는 키가 서로 다른 암호알고리즘

- 비대칭 암호의 요소
    - 송신자 : 한 쌍의 키
    - 수신자 : 한 쌍의 키
        - 이 한 쌍의 키는 공개키, 개인키로 이루어져 있다.
        - 따라서 비대칭 암호를 `공개키암호(public-key cryptography)`라고 부른다.

### 4. 하이브리드 암호 시스템

hybrid cryptosystem

대칭암호와 공개키암호를 조합한 암호방식

둘의 장점을 조합하여 만든 암호시스템

---

## Section 04 그 밖의 암호 기술

### 1. 일방향 해시함수

`해시값` : `일방향 해시함수(one-way hash function)`를 사용하여 계산한 값

- 문서의 무결성 점검
- 데이터가 전송 도중에 변경되었는지 아닌지를 확인할 수 있다.

### 2. 메시지 인증코드

메시지가 생각했던 통신상대로부터 온 것임을 확인하는 코드

변경되지 않았음과 생각한 통신상대로 온 연락임을 확인 가능

- 문서의 무결성과 인증을 제공

### 3. 디지털 서명

`디지털 서명 (digital signature)` : 거짓행세, 변경, 부인같은 위협을 방지하는 기술

- 디지털 서명을 받은 문서를 `검증(verify)`하면 거짓행세나 변경을 찾아내고 부인을 방지할 수 있다.
- 무결성을 확인, 인증과 부인을 방지

`부인(repudiation)` : 통신 사실을 나중에 아니라고 하는 것

### 4. 의사난수 생성기

`의사 난수 생성기(pseudo random number generator; PRNG)` : 난수열을 생성하는 알고리 즘

- 난수는 키 생성(key generation)이라는 중요한 역할을 담당
- 난수알고리즘의 취약하면 키를 추측할 수 있게되어 기밀성 손상 위험

---

## Section 05 암호학자의 도구상자

대칭 암호, 공개 키 암호, 일방향 해시 함수, 메시지 인증 코드. 디지털 서명, 의사난수생성기

이 6가지 기술을 합해서 `암호학자의 도구상자`라고한다.

![IMG_72735D39EBB1-1](https://github.com/love-1006/TIL/assets/163835194/4ad5054b-bcb1-419f-9c02-b91f468f77cc)


---

## Section 06 스테가노그라피와 디지털 워터마킹

`크립토그래피(cryptography)` : 암호를 뜻함. 메시지의 내용을 읽지 못하게 하는 기법

`스테가노그래피(steganography)` : 메시지의 내용을 읽지 못하게 하는 것이 아니라, 메시지의 존재 자체를 숨기는 기법

- 메시지를 숨겨 넣는 방법을 알게 되면 메시지의 내용은 금방 노출
- 최근에는 `디지털 워터마킹(digital watermarking)` 이란 기술에 스테가노그래피가 사용됨 : 파일 중에 저작권자나 구입자의 정보를 집어넣는 기술

---

## Section 07 암호와 보안 상식

### 1. 비밀 암호 알고리즘을 사용하지 말 것

`숨기는 것에 의한 보안(security by obscurity)` 

전문가가 볼 때 위험하고, 어리석은 행위로 간주

- 암호알고리즘의 비밀은 반드시 폭로된다.
    - 역사적으로 암호 알고리즘 비밀이 폭로되지 않은 예는 하나도 없다.
    - 비밀 암호 알고리즘은 구조가 폭로되면 그걸로 끝이지만, 공개 암호 알고리즘은 애초부터 공개되어있다.
- 강한 암호 알고리즘을 만드는 것은 매우 어렵다.

### 2. 약한 암호는 암호화 하지 않는 것보다 위험

사용자는 암호의 강도와 상관없이 ‘암호화 되어있다’는 사실만으로 안심하는 경향이 있다.

→ 이는 기밀성이 높은 정보를 소홀하게 취급할 위험성이 있다.

### 3. 어떤 암호라도 언젠가는 해독된다

어떤 암호라도 모든 키를 하나도 빠짐없이 시도해봄으로서 언젠가는 반드시 해독이 가능하다.

→ 암호문이 해독되기까지의 시간, 암호를 사용하여 지키고 싶은 평문의 가치와 밸런스(tradeoff)가 중요

단, 절대로 해독되지 않는 `일회용패드(one - time pad)` 가 존재하긴 함.

다만 현실적으로 활용하기에는 적합하지 않은 암호

### 4. 암호는 보안의 아주 작은 부분

암호알고리즘을 깨지않더라도 내용을 알 수 있는 방법은 아주 많다.

`사회공학적 공격방법`은 암호의 강도 자체와 아무런 관계가 없다.

- 피싱, 트로이목마, 키로거 등

보안시스템의 강도는 보안 시스템을 구성하는 여러 링크 중 가장 약한 링크의 강도와 같다.

- 가장 약한 링크는 암호가 아닌 사람

---

## Section 08 이 장의 정리

암호의 세계에 등장하는 주요 기술을 살펴보고 암호세계의 상식에 대해 설명하였다.
