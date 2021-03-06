# 운영체제와 데이터베이스

최대 절전모드에서는 RAM있는 데이터를 HDD로 복사해온다. 다시 켰을 때 HDD에서 RAM으로 데이터를 이동시켜 임시데이터를 다시 만든다. 



## 운영체제
운영체제는 시스템 소프트웨어의 종류이다. 
 

### Unix 계열 
### Windows 계열


## 운영체제의 역할
### 시스템 하드웨어 관리
사용자 프로그램의 오류나 잘못된 자원 사용을 감시  
입출력 장치 등의 자원에 대한 연산과 제어를 관리  
CPU Meomory관리도함 
### (가상)시스템 서비스 제공
사용자에게 컴퓨터의 프로그램을 쉽고 효율적으로 실행할 수 있는 환경 제공  
- 기본적인 기능들을 제공  
- 사용자에게 허상의 개념을 어떠한 형상으로 시각적으로 보여줌: ex 폴더구조 등

### 자원관리
컴퓨터 시스템 하드웨어 및 소프트웨어 자원을 여러 사용자간에 효율적 할당, 관리, 보호  
한정적 자원이기 때문에 한계치가 있다. 이를 관리하는것  

- __프로세스 관리__
	- __FCFS(First Come First Served)__ 
		- 준비상태 큐에 도착한 순서에 따라 차례로 CPU할당
	- __SJF(Shortest Job First)__  
	 - 실행시간이 가장 짧은 프로세스에 먼저 CPU할당  
	 - 평균 대기시간이 가장 적은 알고리즘이다.  
	 - 실행시간이 긴 프로세스에 밀려 무한연기발생가능  
	- __Round Robin Scheduling__  
		- 시분할 시스템을 위해 고안됨  
		- FCFS기법 변형  
		- 각프로세스는 시간 할당량 동안만 실행  
		완료되지 않으면 다음 프로세스에게 CPU를 넘겨주고 준비상태 큐의 가장 뒤로 배치  
		- 할당된 시간이 클수록 FCFS와 비슷  
		- 할당시간이 작을 수록 문맥교환과 오버헤드가 자주 발생
	- __Priority Based Scheduling__
		- 프로세스마다 우선순위 부여
		- 우선순위가 동일한 경우 FCFS기법으로 할당
		- 가장 낮은 순위를 부여받은 프로세스의 무한연기발생가능
	- __Multi Queue Scheduling__
		- 프로세스를 특정 그룹으로 분류할 수 있을 경우 그룹에 따라 각기 다른 준비단계 큐 사용
		- 준비상태 큐 마다 다른 스케줄링 기법 사용가능
		- 다른 준비상태 큐로 이동 불가
		- 하위단계 준비 큐에 있는 프로세스를 실행하는 도중이라도 상위단계 준비상태 큐에 프로세스가 들어오면 상위단계 프로세스에게 CPU할당

-

	큐(queue)는 컴퓨터의 기본적인 자료 구조의 한가지로, 먼저 집어 넣은 데이터가 먼저 나오는  
	FIFO (First In First Out)구조로 저장하는 형식을 말한다.   
	영어 단어 queue는 표를 사러 일렬로 늘어선 사람들로 이루어진 줄을 말하기도 하며,  
	먼저 줄을 선 사람이 먼저 나갈 수 있는 상황을 연상하면 된다.
	
	나중에 집어 넣은 데이터가 먼저 나오는 스택과는 반대되는 개념이다.
	프린터의 출력 처리나 윈도 시스템의 메시지 처리기, 프로세스 관리 등 데이터가 입력된 시간 순서대로  
	처리해야 할 필요가 있는 상황에 이용된다.


- __주기억장치 관리__

	- 단순 관리
	- 가상메모리  
		- 보조기억장치를 주기억장치처럼 활용  
		메모리에 공간이 없을 때 보조기억장치를 주기억 장치 처럼 활용하는 것을 가상메모리라고 함(읽고 쓰는 속도가 느림) SSD는 가상메모리로 사용하게 되면 읽고쓰기횟수가 너무 많아져 수명이 짧아지기때문에 가상메모리를 해제하는 것이 좋다.

- __파일관리 __  


>보조기억 장치로 읽고 쓰기 시간이 너무 오래걸려서 주기억장치를 보조기억장치로 사용하는 경우도 있다. `램디스크`   
>운영체제마다 사용하는 파일 시스템이 다르다. filetable작성 규칙도 각기 다름. ex)윈도우에서 사용하던 USB를 Mac에서 쓰면 인식이 안되는 경우	


USER: 연산명령 입력장치 통해 전달
입력장치: 응용프로그램에게 사용자 입력 전달 --(OS)
응용프로그램: 주기억장치로 명령 복사  --(OS)
주기억 장치: CPU로 명령 복사
CPU: 명령 수행 후 주기억장치로 결과 복사
주기억장치: 응용프로그램에 결과 보냄 --(OS)
응용 프로그램: 결과 값을 보조기억장치에 저장 --(OS)
응용프로그램: 결과값을 출력장치로 전달 --(OS)
출력 장치: 사용자에게 결과값 안내

## 멀티테스킹
- 싱글코어 멀티테스킹
- 멀티코어 멀티테스킹


## 데이터베이스
- DataBase (DB)
- 여러 사람에 의해 공유되어 사용될 목적으로 통합하여 관리되는 데이터의 집합
- 통합된 정보들을 저장하여 운영할 수 있는 공용 데이터들의 묶음
- 방대한 데이터를 어떻게 체계적으로 관리 운용 접근할 수 있는지에 대한 논의

__자료구조VS데이터베이스__  
자료구조: 대부분 주기억장치에서 이루어질 내용  
데이터베이스: 대부분 보조기억장치에서 이루어질 내용


### 관계형(RDB) - SQL(Structured Query Language)을 사용하여 질의
### NoSQL - 키-값형, 객체형, 문서형, 컬럼형
### DBMS

>DBMS와 DataBse의 종류는 구분하여 인지해야한다.

DBMS = DataBaseManagementSystem  
데이터베이스에 접근할 수 있는 기능을 제공하는 소프트웨어 즉, 데이터베이스계의 운영체제  
MySQL, PostgreSQL, SQLite, MariaDB

구분 | RDB | NoSQL
--- | --- | ---
형태 | Table (SQL을 사용하여 질의)| Key-value, Document, Column
데이터 | 정형 데이터 | 비정형 데이터
성능 | 대용량 처리시 저하 | 잦은 수정시 저하
스키마 | 고정 | Schemeless
DBMS | Mysql, MariaDB, PostgreSQL | MongoDB, CouchDB, Redis, Cassandra
사용 | User DB or 쉽게 변하지 않는 정보 | one-time-DataBase

### SQL
- Structured Query Language  
- DBMS를 통해 데이터를 관리하기 위한 구조화된 질의문을 작성하기 위한 언어  
- 관계형 데이터베이스 관리 시스템에서 사용


