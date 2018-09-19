# Collathon in cnu

## 콜라톤 목적
> 여러학과 사람들과 협업을 하여 새로운 서비스 창출

## 문제의식: 학생식당에서 결제를 위해서 줄서고, 식사를 받기위해서 음식이 준비가 안 되더라도 줄서는 문제

## 목표: 자리에 앉아서 주문하고 음식이 나오면 호출을 통해서 받으러 간다. 추가 목표로 NFC를 통한 결제(식권 소모)

## 주제: 학생식당 식권 결제 및 호출 웹앱

## 이번에 프로젝트에 해보고 싶은것
1. AMP
2. PWA

### front-end

#### UI

##### consumer

* 로그인
* 회원가입
* 메뉴(리스트 어느 가맹점인지)
* 결제
* 홈화면(주문 상황 파악)
* 나의 주문(호출 확인, 호출시 푸쉬메시지)

##### provider

* 호출 (번호입력으로)
* 상황확인
* 로그인

### Back-end

#### 쓸거?기술?적용?뭐지?

* AWS Lambda
* dynamoDB
* nodejs
* API-gateway
* serverless

#### 필요 API
* 회원가입
    + user
* 로그인
    + user
* 주문상황(가맹점별로 하면 좋지)
    + 가맹점/대기리스트
* 결제(네이버 페이 결제 가정, 가맹점에 등록해야하므로 모킹)
    + user
* 메뉴
    + 가맹점
* 호출
    + 가맹점
    + 주문내역/유저ID
    + user
* 나의 주문내역
    + 주문내역

#### DB
```
user: {
    유저ID: "",
    비밀번호: "",
    최근 선택한 가맹점ID: ""
}

주문내역: {
    주문번호: "",
    유저ID: "",
    가맹점ID: "",
    주문일자: "",
    상품명: "",
}

가맹점: {
    가맹점ID: "",
    가맹점pass: "",
    메뉴:{},
    대기리스트: {
        호출번호: 주문번호
    },
}
```

## 진척상황

* 2018-09-19 - 서버리스 프레임워크 설정 및 람다 다이나모 연동하여(로컬 포함) 배포해놓음
