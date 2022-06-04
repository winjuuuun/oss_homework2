**tos란?**

top는 유닉스 계열 시스템에서 프로세스 목록을 CPU 사용률이 높은 것부터 보여주는 소프트웨어이다.
top명령어는 시스템의 프로세스와 메모리 사용상태를 5초의 간격으로 업데이트하여 화면에 출력한다.
어떤 프로세스가 CPU를 많이 차지하고 있는지 체크할때 실시간으로 보이기 떄문에 유용하다.
윈도우의 작업관리자와 같은 역할!!

***사용방법***
|옵션|설명|
|:---|---|
|-b|배치모드로 정보를 출력합니다. 실시간 상화 대화형모드로 정보를 화면에 일렬로 출력합니다.|
|-d delay|지정한 시간(delay 초)의 간격으로 정보를 업데이트하여 출력합니다.|
|-i idle|토글값이 off일때, idle 프로세스나 좀비 프로세스 정보를 출력하지 않습니다.|
|-n num|지정한 시간(num)만큼 업데이트 정보를 출력합니다.|
|-p pid|지정한 프로세스 ID(pid)의 정보만을 출력합니다.|
|-q|시간의 간격 없이 계속하여 업데이트 정보를 출력합니다.|
|-s|몇 개의 대화식 명령을 비활성화 합니다.|
|-S|누적된 정보를 출력합니다.|

top명령어를 실행한 후 초기화면에서 "h"키를 입력하면 사용할수있는 단축키 목록을 확인할수 있다.

***전체내용***

<img width="402" alt="image" src="https://user-images.githubusercontent.com/106620115/171995545-a203e23d-8bbb-4a87-981b-5b9360f172e1.png">

***첫번째 줄***
<img width="405" alt="image" src="https://user-images.githubusercontent.com/106620115/171995608-436d1c4c-b966-4139-b0e6-34981c0d86f8.png">
**서버 정보를 담고 있는 줄**

top - 12:25:57 >>>> 12시 25분 57초 현재 서버의 시간
up >>> 가동 중
2:30 >>>> 2시간 30분째
2 users >>>> 2명의 사용자가 접속
load average:0.00, 0.00, 0.00 >>> load average(부화율)
***두번째 줄***
<img width="407" alt="image" src="https://user-images.githubusercontent.com/106620115/171995752-2aab4901-731a-468d-bbdb-de13e06ad0d6.png">
**프로세스 정보를 담고 있는 줄**

105 total >>> 총 105개의 프로세스 가동 중
1 running >>> 1개의 프로세스가 실행 중
102 sleeping >>> 102개의 프로세스가 대기 중
2 stoppend >>> 2개의 프로세스가 멈춤
0 zombie >>> 0개의 프로세스 좀비 상태
***세번째 줄***
<img width="401" alt="image" src="https://user-images.githubusercontent.com/106620115/171995870-d65d864c-e8b7-4f6a-be54-30d42a3c5bff.png">
**CPU 정보를 담고 있는 줄**

% us >>> 유저레벨에서 사용하고 있는 CPU 비중
% sy >>> 시스템 레벨에서 사용하고 이쓴 CPU 비중
% id >>> 유휴 상태의 CPU 비중
% wa >>> 시스템이 I/O 요청을 처리하지 못한 상태에서의 CPU idle 상태인 비중
***네번쨰와 다섯번째 줄***
<img width="406" alt="image" src="https://user-images.githubusercontent.com/106620115/171995982-95c8d617-abc1-4669-9055-9ac58d852ca4.png">
**메모리 정보를 담고 있는 줄**

MiB Mem
1827.1 total >>> 전체 물리적인 메모리
1276.4 free >>> 사용되지 않는 여유 메모리
250.5 used >>> 사용중인 메모리
300.2 buff/cache >>> 버퍼된 메모리
Swap
5120.0 total >>> 전체 스왑 메모리
5120.0 free >>> 사용되지 않은 여유 메모리
0.0 used >>> 사용 중인 스왑 메모리
1426.0 avail Mem >>> 캐싱메모리
***그 이 하 내용***
**프로세스 상태**

<img width="407" alt="image" src="https://user-images.githubusercontent.com/106620115/171996307-864fbd84-dfec-4f71-951e-ee70c1847a04.png">

|||
|---|---|
|PID|프로세스 ID(PID)|
|USER|프로세스를 실행시킨 사용자ID|
|PR|프로세스의 우선순위(priority)|
|NI|NICE 값.알의 nice value 값.마이너스를 가지는 nice value는 우선순위가 높음|
|VIRT|가상 메모리의 사용량(SWAP+RES)|
|RES|현재 페이지가 상주하고 있는 크기(Resident Size)|
|SHR|분할된 페이지,프로세스에 의해 사용된 메모리를 나눈 메모리의 총 합|
|S|프로세스의 상태-S(sleeping),R(running),W(swqpped out process),Z(zombies)|
|%CPU|프로세스가 사용하는 CPU의 사용률|
|%MEM|프로세스가 사용하는 메모리의 사용률|
|COMMAND|실행된 명령어|

***ps란?***

**현재 돌아가고 있는 프로세스를 확인할수 있는 명령어로써 top과 함께 ps-ef 명령어를 이용하여 CPU사용률과 사용중인 프로세스를 체크한다.
사용중인 프로그램이 멈추었을때 프로세스가 돌고있는지 확인하고 그 프로세스가 돌고있으면 강제 종료 해줘야한다.**

**ps 명령어**

ps명령어는 현재 실행중인 프로세스 목록과 상태를 보여준다.
ps의 옵션은 전통적인 유닉스인 System V,BSD,GNU에 따라 결과가 다르게 나타나고 표기법에도 차이를 보인다.
옵션 사용시 System V계열은 대시(-)를 사용하고 BSD계열은 대시(-)를 사용하지 않는다.GNU에서의 옵션 표기는 두 개의 대시(--)를 사용한다.
**원하는 프로세스의 상태를 출력하려면 정확한 옵션 사용이 중요!!!**

**ps 사용법**
ps[option]

**특정 프로세스를 확인하는데 주로 grep이라는 명령어와 함께 사용함**
System V 계열에서 ps-ef를 가장 많이 사용,ps -ef|grep '프로세스명'
BSD계열에선 ps aux를 가장 많이 사용,ps aux|grep '프로세스명'

ps
사용자와 관련된 프로세스를 출력해주고 주로 옵션들과 같이 사용되는 경우가 많다.
<img width="240" alt="image" src="https://user-images.githubusercontent.com/106620115/172011790-61e2631b-9310-45aa-8880-ef7738463ebc.png">
**기본적으로 PID(프로세스번호),TTY(프로세스가 연결된 터미널),TIME,CMD 네 개의 정보가 출력

**ps항목**
|항목|의미|
|---|---|
|USER|BSD계열에서 나타나는 항목으로 프로세스 소유자의 이름|
|UID|SYSTEM V계열에서 나타나는 항목으로 프로세스 소유자의 이름|
|PID|프로세스의 식별번호|
|PPID|부모 프로세스 ID|
|%CPU|CPU사용 비율의 추정치(BSD)|
|%MEM|메모리의 사용 비율의 추정치(BSD)|
|VSZ|K단위 또는 페이지 단위의 가상메모리 사용량|
|RSS|실제메모리 사용량|
|TTY|프로세스와 연렬되 터미널|
|S,STAT|현재 프로세스의 상태 코드(S:Sys V,STAT:BSD)}
|TIME|총 Cpu사용시간|
|COMMAND|프로세스의 실행명령행|
|STIME|프로세스가 시작된 시간 혹은 날짜|
|C,CP|짧은 기간동안의 CPU사용률(C:SYs EV,CP:BSD)|
|F|프로세스의 플래그|
|PRI|실제 실행 우선순위|
|NI|nice 우선순위 번호|

**ps명령어 사용 예시**

ps ax:시스템에 동작중인 모두 프로세스를 보고 싶을때 위와 같은 명령어를 사용하면 BSD포맷으로 출력해준다.PID,TTY,STAT,TIME,COMMAND정보가 뜨고 사용자기준의 다양한 정보들을 출력해주고 싶으면 u옵션을 껴서 aux로 구성
ps aux:시스템에 동작중인 모든 프로세스를 소유자 정보와 함께 다양한 정보를 출력(BSD포맷으로 출력)
필드들이 늘어나서 USER,%CPU,%MEM,VSZ,RSS등등 다양한 정보를 한번에 보기 쉽게 출력해준다.ps aux|grep은 특정 프로세스에 대해서 보고 싶을때 사용
Ps -ef:SYstem V계열 옵션 으로 ps aux와 동일 ps -ef|more는 추가로 한 페이지씩 화면에 출력해준다.
UID,PID,PPID,C,STIME,TTY,TIME,CMD정보를 볼수 있다.
ps -el|head:긴 포맷으로 출력하고 싶을때는 -l옵션,F,S,PRI,NI,ADDR 더 많은 정보를 알수있다.
ps -fp[PID]:PID를 키워드로 프로세스 정보를 확인,-p옵션을 써주면 된다.
ps -U root -u root:특정 사용자가 돌리는 프로세스의 정보를 알고 싶을때 real uid와 uid를 의미하는 옵션
ps -t pts/18:특정 TTY에서 실행되는 프로세스 또한 뽑아서 확인할수있다.-t옵션을 사용
ps -e -o pid,ppid,uname,pcpu,pmem,comm,tty|head:-o옵션을 사용하면 원하는 컬럼만 보이도록 포맷을 정할수있다.

**ps명령어 요약**

ps -ㅣ 상세 내용 보여줌
ps -e 모든 프로세스 보여줌
ps -ef 모든 프로세스 모든 정보를 출력
ps -efc c를 추가하여 명령이름까지 보여줌

***jobs란?***

**작업의 상태를 표시하는 명령어로 현재 쉘 세션에서 실행시킨 백 그라운드 작업의 목록이 출력되며, 각 작업에는 변호가 붙어 있어 kill 명령어 뒤에 %번호 등으로 사용할수있다.**
<img width="411" alt="image" src="https://user-images.githubusercontent.com/106620115/172019724-8891c7f6-d74d-4582-91c1-ae1931400d52.png">

|상태|설명|
|---|---|
|Running|작업이 계속 진행중임|
|Done|작업이 완료되어 0을 반환|
|Done(code)|작업이 종료되었으며 0이 아닌 코드를 반환|
|Stopped(SIGTSTP)|SIGTSTP 시그널이 작업을 일시 중단|
|Stopped(SIGTTIN)|SIGTTIN 시그널이 작업을 일시 중당|
|Stopped(SIGTTOU)|SIGTTOU 시크널이 작업을 일시 중단|

**옵션**
|옵션|설명|
|---|---|
|-ㅣ|프로세스 그룹 ID를 state 필드 앞에 출력|
|-n|프로세스 그룹 중에 대표 프로세스 ID를 출력|
|-p|각 프로세스 ID에 대해 한 행씩 출력|
|command|지정한 명령어를 실행|

***kill이란?***

**프로세스를 죽이는것**

**프로세스마다 고유에 PID값이 존재하고 PID값으로 프로세스를 죽인다.-9는 강제종료,-15는 작업 종료**

사용법:

***kill_옵션PID***

<img width="413" alt="image" src="https://user-images.githubusercontent.com/106620115/172021155-c10d0838-50cc-4979-a32a-c744e3542be5.png">
<img width="413" alt="image" src="https://user-images.githubusercontent.com/106620115/172021163-d8b63851-d3a7-40c8-85fb-fb3e691f13f6.png">





