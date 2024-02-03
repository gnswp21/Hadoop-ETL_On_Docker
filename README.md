# Hadoop-ETL_On_Docker


### 목적
도커 컨테이너에 hadoop, kafka, spark, mysql에 올려 독립된 도커 환경에서 하둡 ETL을 실행시켜 보자


### 과정
- [ ] 우분투 컨테이너에 자바, 파이썬 설치 후 이미지로 커밋 (이하 기본 컨테이너)
- [ ] 기본 컨테이너에 하둡 설치, 호스트에서 컨테이너 자바, 하둡 사용할 수 있는지 테스트
- [ ] 기본 컨테이너에 카프카 설치


### 프로젝트 구조



### 사용된 기술

<img src="https://img.shields.io/badge/java-007396?style=for-the-badge&logo=java&logoColor=white"><img src="https://img.shields.io/badge/HADOOP-66CCFF?style=for-the-badge&logo=HADOOP&logoColor=white"><img src="https://img.shields.io/badge/KAFKA-231F20?style=for-the-badge&logo=KAFKA&logoColor=white"><img src="https://img.shields.io/badge/APACHE_SPARK-E25A1C?style=for-the-badge&logo=KAFKA&logoColor=white"><img src="https://img.shields.io/badge/MYSQL-4479A1?style=for-the-badge&logo=KAFKA&logoColor=white">



### 사용 방법

> EtlFileUploader2Hdfs.java : FRED API로부터 하둡 및 로컬에 데이터를 선별 후 저장

> EtlDataUploader2Kafka.java : 하둡파일시스템의 데이터를 카프카 토픽으로 저장

> EtlDataUploader2MySQL.java : 카프카 토픽을 스파크를 통해 불러와 전처리후 MYSQL에 배치로 저장

> EtlDataUploader2MySQLStream.java : : 카프카 토픽을 스파크를 통해 불러와 전처리후 MYSQL에 스트림으로 저장


### 체크
- Utils의 PropertyFileRader는 재사용 가능한 코드
- pom.xml, resources 디렉토리의 버전 및 설정에 유의

### TODO
- json 데이터 -> POJO 다른 데이터로 해보기
- log4j 설정 정리해서 블로깅
- 하둡, 카프카 클러스터 설정


### 버전
- ubuntu lts 22.04
- java 11.0
- anaconda  2020.11 linux 64



---
### 커밋 규칙
| 이름                | 내용                          |
|-------------------|-----------------------------|
| ✨ feat            | 새로운 기능 추가                   |
| 🐛 fix             | 버그 수정                      |
| 📝 docs            | 문서 수정                      |
| 💡 comment         | 필요한 주석 추가 및 변경             |
| 🎨 style           | 코드 포맷팅, 세미콜론 누락, 코드 변경이 없는 경우 |
| ♻️ refactor        | 코드 리팩토링                    |
| 🔧 update          | 코드 업데이트 및 수정              |
| ✅ test            | 테스트 코드                    |
| 📦 chore           | 빌드 업무 수정, 패키지 매니저 수정     |
| 🔥 remove          | 파일을 삭제하는 작업만 수행           |
| 🚚 rename          | 파일 혹은 폴더명을 수정하거나 옮김      |
| 🚑 !HOTFIX         | 급하게 치명적인 버그 고침           |
| 💥 !BREAKING CHANGE | 커다란 API 변경                 |
