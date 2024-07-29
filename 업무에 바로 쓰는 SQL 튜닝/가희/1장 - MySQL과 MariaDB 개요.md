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

