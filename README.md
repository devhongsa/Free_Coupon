# Free_Coupon

### 공짜쿠폰 랜덤추첨 서비스

일반식당, 상점, 프렌차이즈 가리지 않고 자사의 상품을 홍보하고 싶을때 쿠폰을 웹앱 서비스에 등록해 놓으면 소비자들이 주어진 티켓으로 응모를 하고 랜덤추첨을 통해 쿠폰을 얻을 수 있는 서비스입니다.

<br>

## *Tech Stack*
***
+ #### SpringBoot
+ #### Elasticsearch 
+ #### Mysql 
+ #### Redis
+ #### Java11

<br>

## *API 기능*
***

### 공동 API

- 회원가입/로그인 : 파트너/일반유저의 가입폼이 다름
- 회원정보 수정하기 : 정보 수정
- 회원 탈퇴
- 쿠폰 목록 보기 : 응모가능 목록에 올라온 쿠폰들을 보여줌
  - 카테고리별 검색기능 ( 커피/음료, 치킨, 피자, 패스트푸드, 기타외식 .. 등)
  - 검색어로 검색 기능 ( 특정 브랜드 검색 )


### 파트너 회원 전용 API 

- 쿠폰 발급하기 : 파트너 권한을 가진 유저가 자신의 자체 쿠폰을 발급하는 기능, 상품의 이미지도 같이 등록 
- 발급한 쿠폰 목록보기 : 파트너가 자신이 발급한 쿠폰 목록을 볼 수 있는 기능
- 쿠폰 삭제하기 : 발급한 쿠폰 삭제하기 
- 쿠폰 등록하기 : 발급한 쿠폰을 쿠폰 응모가능 목록에 올리기, 같이 올라갈 광고도 선택, 몇장의 쿠폰을 올릴건지도 선택
- 쿠폰 사용 처리하기 : 소비자가 보여준 QR 쿠폰을 찍어 사용처리한다.
- 광고 등록하기 : 쿠폰에 붙을 추가광고 이미지나 url링크 등록 


### 일반 회원 전용 API
- 보유티켓개수 : 쿠폰에 응모할 수 있는 티켓 개수 보기 
- 응모하기 : 쿠폰에 응모하기 
- 응모취소하기 : 응모취소
- 광고보기 : 해당 쿠폰의 광고를 보면 티켓소모없이 응모가능 


### Admin 전용 API 
- 쿠폰 발급 허가하기 : 효용가치가 거의 없는 쿠폰 등록을 배제하기 위해 만든 기능     

<br>


## *ERD*
***
![free_coupon-entity (2)](https://github.com/devhongsa/Free_Coupon/assets/100022877/3b9b06e5-5cb1-4920-b356-19afedc07392)


<br>



