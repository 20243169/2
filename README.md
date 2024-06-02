# Linux 명령어 설명

# 1 `top` 명령어 설명

`top` 명령어는 시스템의 상태를 전반적으로 가장 빠르게 파악 할수있습니다.(CPU, Memory, Process)

## `top` 실행 후 명령어

shift + p : CPU 사용률 내림차순

shit + m : 메모리 사용률 내림차순

shift + t : 프로세스가 돌아가고 있는 시간 순

k : kill. k 입력 후 PID 번호 작성. signal은 9

f : sort field 선택 화면 -> q 누르면 RES순으로 정렬

a : 메모리 사용량에 따라 정렬

b : Batch 모드로 작동

1 : CPU Core별로 사용량 보여줌

# 2 `ps` 명령어
`ps` 명령어는 Process State의 약자로 현재 실행 중인 프로세스와 상태를 출력하는 명령어입니다. 

## `ps` 명령어 출력 항목
| 출력항목                  | 설명                                         |
|---------------------------|----------------------------------------------|
| USER (BSD) UID (System V) | 프로세스 소유자의 이름                       |
| PID                       | 프로세스의 식별 번호                         |
| PPID                      | 부모 프로세스의 PID                          |
| %CPU                      | CPU 사용 비율의 추정치 (BSD)                 |
| %MEM                      | Memory 사용 비율의 추정치(BSD)               |
| VSZ                       | K 단위 또는 페이지 단위의 가상 메모리 사용량 |
| RSS                       | 실제 메모리 사용량                           |
| TTY                       | 프로세스와 연결된 터미널                     |
| S (System V) STAT (BSD)   | 현재 프로세스의 상태 코드                    |
| TIME                      | 총 CPU 사용 시간                             |
| COMMAND                   | 프로세스의 실행 명령행                       |
| STIME                     | 프로세스가 시작된 시간 혹은 날짜             |
| C (System V) CP (BSD)     | 짧은 기간 동안의 CPU 사용률                  |
| F                         | 플래그                                       |
| PRI                       | 실제 실행 우선순위                           |
| NI                        | nice 우선순위 번호                           |

# 3 `jobs` 명령어 설명

`jobs` 명령어는 백그라운드로 실행 중인 프로세스나 현재 중지된 프로세스의 목록을 출력해 주는 명령입니다.

## 사용법
jobs[옵션][작업명]

## 주요옵션 설명

| 옵션 | 설명                                      |
|------|-------------------------------------------|
| -l   | 각 작업의 PID를 포함한 자세한 정보를 표시 |
| -n   | 최근에 상태가 변경된 작업만 표시          |
| -p   | 각 작업의 PID만 표시                      |
| -r   | 현재 실행 중인 작업만 표시                |
| -s   | 중지된 작업만 표시                        |

# 4 `kill` 명령어 설명

`kill` 명령어는 리눅스와 유닉스 시스템에서 프로세스를 종료하는 데 사용됩니다. 일반적으로 PID (프로세스 ID)를 지정하여 해당 프로세스를 종료합니다.

## 사용법
kill [옵션] <PID>

## 주요옵션 설명
| 옵션 | 의 미                                                         |
|:----:|---------------------------------------------------------------|
|  -9  | 프로세스아이디(PID)를 직접 지정하여 종료시 사용 됩니다        |
|  -l  | 신호(Signal)로 사용할 수 있는 신호(Signal) 이름들을 보여준다. |

## 예시
```bash
# kill -l
 1) SIGHUP	 2) SIGINT	 3) SIGQUIT	 4) SIGILL	 5) SIGTRAP
 6) SIGABRT	 7) SIGBUS	 8) SIGFPE	 9) SIGKILL	10) SIGUSR1
11) SIGSEGV	12) SIGUSR2	13) SIGPIPE	14) SIGALRM	15) SIGTERM
16) SIGSTKFLT	17) SIGCHLD	18) SIGCONT	19) SIGSTOP	20) SIGTSTP
21) SIGTTIN	22) SIGTTOU	23) SIGURG	24) SIGXCPU	25) SIGXFSZ
26) SIGVTALRM	27) SIGPROF	28) SIGWINCH	29) SIGIO	30) SIGPWR
31) SIGSYS	34) SIGRTMIN	35) SIGRTMIN+1	36) SIGRTMIN+2	37) SIGRTMIN+3
38) SIGRTMIN+4	39) SIGRTMIN+5	40) SIGRTMIN+6	41) SIGRTMIN+7	42) SIGRTMIN+8
43) SIGRTMIN+9	44) SIGRTMIN+10	45) SIGRTMIN+11	46) SIGRTMIN+12	47) SIGRTMIN+13
48) SIGRTMIN+14	49) SIGRTMIN+15	50) SIGRTMAX-14	51) SIGRTMAX-13	52) SIGRTMAX-12
53) SIGRTMAX-11	54) SIGRTMAX-10	55) SIGRTMAX-9	56) SIGRTMAX-8	57) SIGRTMAX-7
58) SIGRTMAX-6	59) SIGRTMAX-5	60) SIGRTMAX-4	61) SIGRTMAX-3	62) SIGRTMAX-2
63) SIGRTMAX-1	64) SIGRTMAX

