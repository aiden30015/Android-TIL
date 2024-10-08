# Git

## 정의

- 로컬에서 관리되는 버전 관리 시스템
- 로컬 저장소를 사용하기 때문에 , 다른사람이 나의 작업 내용을 알 수 없음
  특정 시점에서 파일들의 상태를 저장하고 보여주는 버전관리 시스템의 한 종류 이다.

## 특징

1. 빠르다  
   다른 버전 시스템과 달리 git은 변경된 파일 전체를 저장하지 않고, 스냅샷 방식을 이용하여 수정된 내용만 저장하기 때문에 적은 용량을 차지한다.
2. 거의 모든 명령을 로컬에서 실행한다.  
   거의 모든 명령이 로컬의 파일과 데이터만 사용한다.  
   프로젝트의 히스토리 조회 시 서버 없이 로컬에서 조회하고, 오프라인 상태에서도 작업이 가능하다.
3. 무결성  
   파일을 이름으로 저장하지 않고 파일의 내용이나 디렉토리 구조를 이용하여 체크섬을 구하고 SHA-1 해시를 사용하여 40자 길이의 16진수 문자열로 저장한다.
