# DEEPSCAN
  
## 프로젝트 주제
차량 물류 정보 시스템에서 발생하는 차량 인식 오류를 개선하고, 고철장 관리 웹서비스 기능을 제공  
  
## 프로젝트 기간
2025-01-13 ~ 2025-02-20  
  
## 팀 구성
|      담당      |  이름   |             GITHUB              |
|:------------:|:-----:|:-------------------------------:|
|  FRONT-END   |  김좌현  |  https://github.com/jwahyunkim  |
|   BACK-END   |  이준영  |   https://github.com/eecsjlee   |
|     DATA     |  박래찬  |  https://github.com/chani1352   |
  
## 수행역할
백엔드, 데이터베이스 설계, 보안 및 인증 관리  
Spring Boot와 MariaDB을 활용한 RESTful API 설계 및 개발  
AI 모델 결과를 저장하고 불러오는 데이터베이스 구축  
JWT 기반 사용자 인증 및 권한 관리 구현  
  
## 개발환경
IntelliJ IDEA  
Spring Boot version '3.4.1'  
MariaDB '10.11.10'  
  
## 시스템 아키텍처
![image](https://github.com/user-attachments/assets/a4eba6f7-c3c0-41a6-bb78-6d0a412079c7)
  
## ERD
![ERD](https://github.com/user-attachments/assets/57f8a2de-bb92-422b-808e-0a974f51b566)
`transaction 테이블`: 차량의 입차 및 출차 정보를 관리하고 고철의 무게값을 저장하는 테이블  
`car 테이블`: 차량 등록 테이블  
`member 테이블`: 사업자등록번호(brn) 등록 및 회사 등록 테이블  
`scrap_type 테이블`: 고철 종류를 관리하는 테이블  
`scrap_price 테이블`: 고철의 가격을 날짜 단위로 기록하는 테이블  
`missing_records 테이블`: 입차한 기록이 없는 차량을 관리하는 테이블  
  
## 트러블 슈팅
  
### @ManyToOne + @OneToMany 양방향 관계 순환 참조 문제
  
Jackson을 사용하여 JSON 직렬화를 수행할 때, 무한 루프가 발생할 가능성이 있음.  
  
### 정적 이미지 변경 후 서버 재시작 필요 문제
  
src/main/resources/static/ 폴더에 차량 번호판 이미지를 저장했으나, 프론트엔드에서 즉시 반영되지 않고 서버를 재시작해야만 변경사항이 보이는 문제 발생.
