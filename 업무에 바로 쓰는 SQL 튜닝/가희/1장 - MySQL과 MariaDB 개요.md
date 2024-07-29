# 1장 - MySQL과 MariaDB 개요

### DB 버전 확인

```json
> show variables like 'version';

> SELECT @@version;
```

### 오라클 , Mysql의 차이 - 구조적 차이

- 오라클과 MySQL을 실제 서비스에 도입할 경우 장애 예방 효과 또는 장애 발생시 가용성을 기대하며 이중화 구조로 구축한다.
    - 가용성 수준에 따라서, 3중화 구조도 사용

- 데이터가 저장되는 스토리지의 구조 측면에서 큰 차이를 보임
    - 오라클 DB는 통합된 스토리지 하나를 공유
    - MySQL은 물리적인 DB서버마다 독립적으로 스토리지를 할당하여 구성

![image](https://github.com/user-attachments/assets/c57dba45-3854-4f9c-8c0d-6c070baeeca2)


- 이중화를 위한 클러스터, 복제로 운영시에 master-slave등으로 crud 를 구분해서 역할을 수행한다.
- 따라서 SQL 쿼리 튜닝을 진행하더라도, 어느 DB에서 해당 구문이 수행되는지 DB위치를 파악하는게 중요하다.
    - 파악하지 못한다면 말짱 꽝~
    
    Ex) 마스터 노드에서 CUD를 수행, slave에서 R을 수행할 경우, update문에 대한 쿼리튜닝을 슬레이브 노드에서 수행하면 정상적인 쿼리 튜닝 결과가 도출되지 않음
