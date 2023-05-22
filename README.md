#### [2023-1] 오픈소스 SW 개론
# Introduction to Open Source SW 
## README 작성 과제
 리눅스 명령어 중에서 top, ps, jobs, kill 명령어에 대해서 조사하여 README 파일에 작성 후 제출하기

### [top]
  - **개념**
    - 시스템 프로세스/메모리 사용 현황을 실시간으로 출력함
    - 시스템의 프로세스/메모리 사용 상태를 5초의 간격으로 업데이트하여 출력함
    - 기본값은 현재시간, 시스템 업데이트(1) 시간, 시스템에 로그인한 사용자 수, 지난 1분, 지난 5분, 지난 15분간의 시스템 평균 부하
    - top 명령어를 실행한 후 초기 화면에서  키를 입력하면 사용할 수 있는 단축키 목록을 확인할 수 있음
  - **top 기본 문법**
  
    `
    top [옵션]
    `
  - **top 옵션** 
  
    |명령어|내용|
    |:------:|:---|
    |-b | 배치모드로 정보를 출력한다. 실시간 상화 대화형모드로 정보를 화면에 일렬로 출력|
    |-d delay|지정한 시간(delay 초)의 간격으로 정보를 업데이트하여 출력|
    |-i idle|토글값이 off일 때, idle 프로세스나 좀비 프로세스 정보를 출력하지 않음|
    |-n num|지정한 시간(num)만큼 업데이트 정보를 출력|
    |-p pid|지정한 프로세스 ID(pid)의 정보만을 출력|
    |-q|시간의 간격 없이 계속하여 업데이트 정보를 출력|
    |-s|몇 개의 대화식 명령을 비활성화(시큐어 모드)|
    |-S|누적된 정보를 출력(cumulative 모드)|

   - **top 명령어 사용 예시**
    
     ![스크린샷, 2023-05-22 08-54-33](https://github.com/SoojeeLee/intossw/assets/109313822/799e5d5e-c039-496f-9d40-6087e509e756)

---

### [ps]
  - **개념**
    - 프로세스의 현재 상태 출력 
  - **ps 기본 문법**
  
    `
    ps [옵션]
    `
  - **ps 옵션** 
    * 전체 프로세스와 관련된 옵션
  
       |명령어|내용|
       |:------:|:---|
       |-A | 모든 프로세스를 출력|
       |-N | -A 옵션과 비슷하나 ps 프로세스를 제외하고 출력|
       |-a | 세션 리더 및 터미널에 속하지 않는 프로세스를 제외하고 출력|
       |-d | 세션 리더를 제외한 모든 프로세스를 출력|
       |-e | 커널 프로세스를 제외한 모든 프로세스를 출력|
       |T | 현재 터미널에서의 모든 프로세스를 출력|
       |a | 현재 터미널의 사용자 고유 프로세스를 출력|
       |r | 현재 실행 중인 프로세스를 출력|
       |x | 터미널이 없는 프로세스를 출력|
       |--deselect | -N 옵션과 같음|

     * 특정 프로세스를 선택하여 보여주는 옵션
       |명령어|내용|
       |:------:|:---|
       |-C | 지정한 명령어의 이름에 관련된 정보를 출력|
       |-G | 그룹 ID에 관련된 정보를 출력(이름도 지원)|
       |-U | 사용자 ID에 관련된 정보를 출력(이름도 지원)|
       |-g | 지정한 세션 리더 혹은 그룹명에 관련한 정보를 출력|
       |-p | 프로세스 ID를 출력|
       |-s | 세션에 속한 프로세스를 지정|
       |-t | tty를 지정|
       |-u | 사용자 ID를 지정(이름도 지원)|
       |U | 지정한 사용자의 프로세스를 출력|
       |p | 프로세스 ID를 지정|
       |t | tty를 지정|
       |--Group | 실제 그룹 이름이나 ID를 지정|
       |--User | 실제 사용자 이름이나 ID를 지정|
       |--group | 유효 사용자 이름이나 ID를 지정|
       |--pid | 프로세스 ID를 지정|
       |--sid | 세션 ID를 지정|
       |--tty | 터미널을 지정|
       |--user | 유효 사용자 이름이나 ID를 지정|
       |-123 | --sid 123과 같은 의미|
       |123 | --pid 123과 같은 의미|

    * 출력 결과 필드를 제어하는 옵션
       |명령어|내용|
       |:------:|:---|
       |-0 | PID, TTY, STAT, TIME, COMMAND 등의 필드 목록을 출력|
       |-c | PID, CLS, PRI, TTY, TIME. CMD 등의 필드 목록을 출력|
       |-f | UID, PID, PPID, C, STIME, TTY, TIME, CMD 등의 필드를 CMD 필드의 전체 명령어 형태로 출력|
       |-j | PID, PGID, SID, TTY, TIME, CMD 등의 필드 목록을 출력|
       |-l| F, S, UID, PID, PPID, C, PRI, NI, ADDR, SZ, WCHAN, TTY, TIME, CMD 필드의 상세 정보를 출력|
       |-o| 사용자가 정의한 포맷을 지정|
       |-y | -l 이나 l 옵션과 함께 ADDR 필드를 RSS 필드로 출력|
       |0 | PID, TTY, STAT, IME COMMAND 필드 정보를 출력|
       |X | PID, STACKP, ESP, EIP, TMOUT, ALARM, STAT, TTY, TIME, COMMAND 필드의 정보를 리눅스 i386 레지스터 형식으로 출력|
       |j | PPID, PID, PGID, SID, TTY, TPGID, STAT, UID, TIME, COMMAND 필드의 정보를 작업 제어에 관련된 형식으로 출력|
       |l | F, S, UID, PID, PPID, C, PRI, NI, ADDR, SZ, PSS, WCHAN, TTY, TIME, CMD 필드의 정보를 출력하고 -l 옵션과 함께 PSS 필드를 추가하여 출력|
       |o | 사용자 지정 형식으로 출력|
       |s | UID, PID, PENDING, BLOCKED, IGNORED, CAUGHT, STAT, TTY, TIME, COMMAND 필드의 정보를 출력|
       |u | USER, PID, %CPU, %MEM, VSZ, RSS, TTY, STAT, START, TIME, COMMAND 필드의 정보를 출력|
       |v | PID, TTY, STAT, TIME, MAJFL, TRS, DRS, RSS, %MEM, COMMAND 필드의 정보를 출력|
       |--format | 사용자 지정 형식으로 출력|

    * 출력 필드의 내용을 변경하는 옵션
       |명령어|내용|
       |:------:|:---|
       |-H | 프로세스를 계층형으로 출력|
       |-m | 스레드 정보를 출력|
       |-n namelist | 시스템 이름 리스트 파일(namelist)을 지정|
       |-w | 너비에 맞게 잘려진 내용을 제한이 없는 너비의 내용으로 상세하게 출력|
       |--cols | 스크린의 너비를 설정|
       |--columns | 스크린의 너비를 설정|
       |--cumulative | 죽은 자식 프로세스 데이터를 포함하여 출력|
       |--forest | 아스키 문자의 프로세스 트리 형태로 출력|
       |--html | HTML 이스케이프로 출력|
       |--headers | 헤더 라인을 반복|
       |--no-headers | 헤더를 보이지 않음|
       |--lines | 스크린의 높이를 설정|
       |--rows | 스크린의 높이를 설정|
       |--sort | 정렬 방식을 지정. --sort＝[+|-]key[,[+|-]key[,···].|
       |C | CPU 시간을 이용|
       |N | 지정한 시스템 이름의 리스트 파일을 사용|
       |O | 정렬 순서 지정하기 위한 옵션으로 O[+|-]K[,[+|-]K[,···]]의 형식으로 지정. +는 오름차순 정렬, –는 내림차순 정렬|
       |S | 죽은 자식 프로세스의 데이터를 포함|
       |c | 시스템 내부에 보관 중인 명령어 이름을 출력|
       |e | 명령어에 대한 매개 변수와 함께 환경 변수를 출력|
       |f | 아스키(*) 아트로 프로세스 트리를 출력|
       |h | 헤더 라인은 출력하지 않음|
       |m | 모든 스레드 정보를 출력|
       |n | WCHAN과 USER 필드를 숫자 값으로 출력|
       |w | 필드의 너비에 맞게 잘려진 내용을 너비보다 상세하게 출력|
       |--cols | 스크린의 너비를 설정|
       |--columns | 스크린의 너비를 설정|
       |--cumulative | 죽은 자식 프로세스 데이터를 포함|
       |--forest | 아스키 아트의 프로세스 트리를 출력|
       |--html | HTML 이스케이프를 출력|
       |--headers | 헤더 라인을 반복|
       |--no-headers | 헤더를 출력하지 않음|
       |--lines | 스크린의 높이를 설정|
       |--rows | 스크린의 높이를 설정|
       |--sort | 지정한 정렬 방식으로 출력. --sort＝[+|-]key[,[+|-]key[,···] 형식|
       
    * 프로그램의 정보
       |명령어|내용|
       |:------:|:---|
       |-V | 버전 정보를 출력|
       |L | 모든 형태의 지시자를 출력|
       |V | 버전 정보를 출력|
       |--help | 사용법을 출력|
       |--info | 디버깅 정보를 출력|
       |--version | 버전 정보를 출력|
       
<br>

   - **ps 명령어 사용 예시**
     * PID, TTY, TIME, CMD 헤더의 필드와 내용을 출력  
       ![스크린샷, 2023-05-22 09-41-37](https://github.com/SoojeeLee/intossw/assets/109313822/68b44e81-f53c-462c-884f-9e4b9ed639c0)

---

### [jobs]
  - **개념**
    - 작업이 중지된 상태, 백그라운드로 진행 중인 작업 상태, 변경되었지만 보고되지 않은 상태 등을 표시
      * jobs 명령어로 확인할 수 있는 상태값
        |상태|설명|
        |:------:|:---|
        |Running|작업이 일시 중단되지 않았고 종료하지 않고 계속 진행|
        |Done|작업이 완료되어 0을 반환하고 종료|
        |Done|(code)작업이 정상적으로 완료했으며, 0이 아닌 코드를 반환|
        |Stopped|작업이 일시 중단|
        |Stopped|(SIGTSTP)SIGTSTP 신호가 작업을 일시 중단|
        |Stopped|(SIGSTOP)SIGSTOP 신호가 일시 중단|
        |Stopped|(SIGTTIN)SIGTTIN 신호가 작업을 일시 중단|
        |Stopped|(SIGTTOU)SIGTTOU 신호가 작업을 일시 중단했음|
  - **jobs 기본 문법**
  
    ```
    jobs [옵션][jobID]
    jobs -x command [args]
    ```
  - **jobs 옵션** 
  
    |명령어|내용| 
    |:------:|:---|
    |-l |프로세스 그룹 ID를 state 필드 앞에 출력|
    |-n |프로세스 그룹 중에 대표 프로세스 ID를 출력|
    |-p |각 프로세스 ID에 대해 한 행씩 출력|
    |command |지정한 명령어를 실행|

   - **jobs 명령어 사용 예시**
     * 현재 환경의 작업 상태를 아래와 같이 확인(-l 옵션을 이용하여 state 필드 앞에 프로세스 ID를 함께 출력)
       ![스크린샷, 2023-05-22 10-08-27](https://github.com/SoojeeLee/intossw/assets/109313822/6917c50c-82ea-44e6-bc33-e62647136f69)

---
 
### [kill]
  - **개념**
    - 프로세스에 종료 시그널을 보냄 
    - 시스템에 얘기치 않은 문제가 생긴 프로세스를 종료시킬 수 있음
    - ps 명령어와 함께 사용
      - ps를 이용하여 프로세스 확인 후 kill을 이용하여 종료
    - 만일 kill 명령으로 종료되지 않는 프로세스는 -9 옵션을 사용해서 강제로 종료 가능
  - **kill 기본 문법**
  
    ```
    kill [-s 시그널 ][-a] pID
    kill -l [시그널]
    ```
  - **kill 옵션** 
  
    |명령어|내용| 
    |:------:|:---|
    |pid ··· | 종료시킬 프로세스 ID나 프로세스 이름을 지정|
    |-s | 전달할 시그널의 종류를 지정. 여기에는 시그널 이름이나 번호를 써줌|
    |-l | 시그널로 사용할 수 있는 시그널 이름들을 보여줌. 이것은 /usr/include/linux/signal.h 파일에서도 알 수 있음|
    |-1, -HUP| 프로세스를 재활성화|
    |-9 | 프로세스를 강제로 종료시킴|

   - **kill 명령어 사용 예시**
     1. ps 명령어로 sshd 프로세스 확인
     
       ![스크린샷, 2023-05-22 10-22-43](https://github.com/SoojeeLee/intossw/assets/109313822/d2c49505-1a7c-48f7-963b-1c3a95404f43)
       
     2. kill 명령어를 이용하여 종료
     
       ![스크린샷, 2023-05-22 10-22-47](https://github.com/SoojeeLee/intossw/assets/109313822/b7b6e67a-4904-4460-87e3-e9cd83a7e944)
