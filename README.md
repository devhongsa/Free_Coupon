# Free_Coupon

### 공짜쿠폰 랜덤추첨 서비스

일반식당, 상점, 프렌차이즈 가리지 않고 자사의 상품을 홍보하고 싶을때 쿠폰을 웹앱 서비스에 등록해 놓으면 소비자들이 주어진 티켓으로 응모를 하고 랜덤추첨을 통해 쿠폰을 얻을 수 있는 서비스입니다.

<br>

## *Tech Stack*
***
+ #### SpringBoot
+ #### Spring Security
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

- 쿠폰 템플릿 생성하기 : 쿠폰 기본 템플릿을 생성, 쿠폰 등록의 편의성과 유연성 제공 
- 템플릿 수정하기 : 템플릿 정보를 수정할 수 있다. 템플릿 정보 중에 수정을 못하는 정보 존재 (쿠폰카테고리, 쿠폰의 가치, 쿠폰 이름)
- 템플릿 삭제하기 : 템플릿 삭제
- 템플릿 쿠폰 목록보기 : 쿠폰 템플릿 목록 보기 
- 발급 쿠폰 목록보기 : 발급된 QR쿠폰 목록을 보여준다.
- 쿠폰 등록하기 : 템플릿 쿠폰을 쿠폰 응모가능 목록에 올리기, 몇장의 쿠폰을 올릴건지도 선택, (후순위 기능: 같이 올라갈 광고선택)
- 쿠폰 사용 처리하기 : 소비자가 보여준 QR 쿠폰을 사용처리한다.
- (후순위 기능) 광고 등록하기 : 쿠폰에 붙을 추가광고 이미지나 url링크 등록 


### 일반 회원 전용 API
- 보유티켓개수 : 쿠폰에 응모할 수 있는 티켓 개수 보기 
- 응모하기 : 쿠폰에 응모하기 
- 응모취소하기 : 응모취소
- 당첨쿠폰 목록 보기 : 당첨된 쿠폰 목록을 볼 수 있다
- (후순위 기능 ) 광고보기 : 해당 쿠폰의 광고를 보면 티켓소모없이 응모가능 


### Admin 전용 API 
- 쿠폰 발급 허가하기 : 효용가치가 거의 없는 쿠폰 등록을 배제하기 위해 만든 기능
- (후순위 기능) : 당첨된 유저에게 당첨소식을 알리는 기능 (휴대폰번호 혹은 이메일로 알림)

<br>


## *ERD*
***
![free_coupon-entity의 복사본](https://github.com/devhongsa/Free_Coupon/assets/100022877/dbe7e10e-2b93-4ed3-a653-2f1213aefdb4)

- User : 일반 유저 테이블 
- Partner : 파트너 유저 테이블 
- Coupon_Template : 파트너의 쿠폰템플릿 테이블. 파트너가 쿠폰 템플릿을 만들어놓으면 템플릿을 사용해서 쿠폰 재등록시 편의성을 제공 
- Coupon_Feed : 파트너가 쿠폰을 등록하면, 응모가능 쿠폰 목록에 등록되게 됨. Elasticsearch 사용 ( 쿠폰 검색기능을 위함 )
- Coupon_Qr : 쿠폰 추첨이 완료되면 QR쿠폰이 생성되고 당첨된 유저의 쿠폰당첨목록에 쿠폰정보가 보여지게 됨.

<br>



