## 3장 - SQL 튜닝

### 3.1 실습 환경 구성하기


* 로컬 데이터베이스 목록 조회
  <img width="475" alt="스크린샷 1" src="https://github.com/user-attachments/assets/ed41d578-5026-40e5-93bf-e6069144356c">


* 데이터 존재 여부 확인
  <img width="345" alt="스크린샷 2" src="https://github.com/user-attachments/assets/74b3f2a8-e1c8-46ce-bbbb-2a0756f14def">


### 3.2 실행 계획 수행


* MySQL 실행 계획 수행
  <img width="926" alt="스크린샷 3" src="https://github.com/user-attachments/assets/2b3aab6f-ab78-45cb-815a-ad4d92d970d2">


* 기본 실행 계획 항목 분석 - id
  <img width="1119" alt="스크린샷 4" src="https://github.com/user-attachments/assets/ddc658ef-d017-43be-a3fe-d45f86073bf5">


* 기본 실행 계획 항목 분석 - select_type (simple)
  <img width="908" alt="스크린샷 5" src="https://github.com/user-attachments/assets/83543891-d662-4ed9-a875-accd0ea97650">
  <img width="1090" alt="스크린샷 6" src="https://github.com/user-attachments/assets/9a5f9b3e-4e4d-4d0d-b3af-1fccef8acc04">


* 기본 실행 계획 항목 분석 - select_type (primary)
  <img width="1115" alt="스크린샷 7" src="https://github.com/user-attachments/assets/e2421448-6eea-4530-a6cd-4a4aa1a71648">
  <img width="1415" alt="스크린샷 8" src="https://github.com/user-attachments/assets/c02b0d96-4c7b-4ba1-9618-c5c4bdd7c8bb">


* 기본 실행 계획 항목 분석 - select_type (subquery)
  <img width="1041" alt="스크린샷 9" src="https://github.com/user-attachments/assets/2f9d7287-26c7-43e1-8efe-f1514fafe6e1">


* 기본 실행 계획 항목 분석 - select_type (derived)
  <img width="1025" alt="스크린샷 10" src="https://github.com/user-attachments/assets/9ee7ba23-46c5-4fa5-a8ec-bc37af2d5641">


* 기본 실행 계획 항목 분석 - select_type (union)
  <img width="730" alt="스크린샷 11" src="https://github.com/user-attachments/assets/a5188c23-d813-42eb-8da7-b94fa4c45ee0">


* 기본 실행 계획 항목 분석 - select_type (union result)
  <img width="724" alt="스크린샷 12" src="https://github.com/user-attachments/assets/8f0b2af9-7e3b-41be-ad5b-fc47c0e87cee">


* 기본 실행 계획 항목 분석 - select_type (dependent subquery)
  <img width="744" alt="스크린샷 13" src="https://github.com/user-attachments/assets/41d281c5-6655-4d76-b815-fc156a601cee">


* 기본 실행 계획 항목 분석 - select_type (dependent union)
  <img width="744" alt="스크린샷 13" src="https://github.com/user-attachments/assets/41d281c5-6655-4d76-b815-fc156a601cee">


* 기본 실행 계획 항목 분석 - select_type (uncacheable subquery)
  <img width="739" alt="스크린샷" src="https://github.com/user-attachments/assets/da3849e3-b615-47e1-9af4-e2dc29e3fb2c">


* 기본 실행 계획 항목 분석 - select_type (materialized)
  <img width="734" alt="스크린샷" src="https://github.com/user-attachments/assets/26554847-b844-4dcf-82e8-cb70385309e6">


* 기본 실행 계획 항목 분석 - table
  <img width="737" alt="스크린샷 " src="https://github.com/user-attachments/assets/029a8cf2-b6d8-41c6-a5d0-951ab402b76a">


* 기본 실행 계획 항목 분석 - type (system)
  <img width="742" alt="스크린샷 " src="https://github.com/user-attachments/assets/a583287e-e033-4b77-8113-0e28703294eb">


* 기본 실행 계획 항목 분석 - type (const)
  <img width="734" alt="스크린샷" src="https://github.com/user-attachments/assets/3f6285e1-9ff9-4d49-aa9d-7fe192560b1e">


* 기본 실행 계획 항목 분석 - type (eq_ref)
  <img width="733" alt="스크린샷" src="https://github.com/user-attachments/assets/13106e25-14cc-4a5d-988c-a956959a2a5a">


* 기본 실행 계획 항목 분석 - type (ref)
  <img width="766" alt="스크린샷 " src="https://github.com/user-attachments/assets/61906d30-9b83-44a9-98aa-1beac9be6e8f">
  <img width="771" alt="스크린샷" src="https://github.com/user-attachments/assets/2b1da9cd-007d-44cd-9570-67c51d749502">


* 기본 실행 계획 항목 분석 - type (ref_or_null)
  <img width="772" alt="스크린샷" src="https://github.com/user-attachments/assets/60e9edff-4cd5-4fcb-aa76-7a53623b1fe5">


* 기본 실행 계획 항목 분석 - type (range)
  <img width="770" alt="스크린샷" src="https://github.com/user-attachments/assets/709dba06-47e4-45c2-8ff0-a8bb05524848">


* 기본 실행 계획 항목 분석 - type (index_merge)
  <img width="768" alt="스크린샷 " src="https://github.com/user-attachments/assets/4ef4afca-cfdb-4bb6-96c1-1c0cb2422909">


* 기본 실행 계획 항목 분석 - type (index)
  <img width="743" alt="스크린샷 " src="https://github.com/user-attachments/assets/83dc3ba5-6e2d-4df4-a8f9-ef4dcd0c186f">


* 기본 실행 계획 항목 분석 - type (all)
  <img width="771" alt="스크린샷 " src="https://github.com/user-attachments/assets/ca164fd9-3d01-491d-bb6b-1daad264082f">


* 기본 실행 계획 항목 분석 - key
  <img width="766" alt="스크린샷" src="https://github.com/user-attachments/assets/a4380706-4ecb-4cfd-8207-92419dee55b6">


* 기본 실행 계획 항목 분석 - key_len
  <img width="743" alt="스크린샷 " src="https://github.com/user-attachments/assets/83dc3ba5-6e2d-4df4-a8f9-ef4dcd0c186f">


* 기본 실행 계획 항목 분석 - ref
  <img width="768" alt="스크린샷" src="https://github.com/user-attachments/assets/41623ec7-8f25-43a0-82bd-8d1615034412">


* 기본 실행 계획 항목 분석 - extra (using index)
  <img width="745" alt="스크린샷" src="https://github.com/user-attachments/assets/1a357bcd-05d0-408e-be08-cbbf0fd16aad">


* MySQL의 확장된 실행 계획 수행 (explain format = traditional)
  <img width="766" alt="스크린샷" src="https://github.com/user-attachments/assets/4a19fa38-2f4c-405b-9307-6f3851c9d5ce">


* MySQL의 확장된 실행 계획 수행 (explain format = tree)
  <img width="768" alt="스크린샷" src="https://github.com/user-attachments/assets/4ece992f-f9f4-49b0-b387-23730d3a4527">


* MySQL의 확장된 실행 계획 수행 (explain format = json)
  <img width="1200" alt="스크린샷" src="https://github.com/user-attachments/assets/f3e299ae-8827-48dc-a023-2ab8c0e485a7">


* MySQL의 확장된 실행 계획 수행 (explain analyze)
  <img width="741" alt="스크린샷" src="https://github.com/user-attachments/assets/3bd1ec5a-bac9-4f50-b629-77be5b825e6d">




### 3.3 프로파일링


* SQL 프로파일링 실행
  <img width="555" alt="스크린샷" src="https://github.com/user-attachments/assets/ad274f0b-f918-4135-8a91-b0ba2cac62ea">
  <img width="706" alt="스크린샷" src="https://github.com/user-attachments/assets/67187403-12e7-41de-b39a-36cc8b5b6ca2">
  <img width="740" alt="스크린샷" src="https://github.com/user-attachments/assets/3d0a6010-50e2-4a9d-8d08-fecb4a43776e">


* 프로파일링 결과 해석하기
  <img width="745" alt="스크린샷" src="https://github.com/user-attachments/assets/2d0a0c23-831a-44ad-bca7-295a415ca827">
  <img width="623" alt="스크린샷" src="https://github.com/user-attachments/assets/46ca0956-7d8f-4692-ba79-11fca2219a09">
  <img width="621" alt="스크린샷 " src="https://github.com/user-attachments/assets/43605357-5e38-4cc0-bf8e-7c7133956445">
