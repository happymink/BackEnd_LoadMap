## OS(Operating System)란?
운영체제는 컴퓨터 시스템의 각종 자원을 효율적으로 관리하고 컴퓨터 HW(Hard Ware)와 User간의 인터페이스를 담당하는 시스템 프로그램이다.

## OS의 목적

OS는 사람이 HW와 SW를 **편리하게 사용**하며 컴퓨터의 **성능을 높여**주는 것이 1차 목적이다. 특징은 4가지로 나누어 볼 수 있다.

1. 처리능력의 향상 : 일정한 단위 시간 내에 처리할 수 있는 일의 양, 수치가 높을 수록 좋다.

2. 반환시간의 최소화 : 어떠한 작업을 시작한 시간부터 끝날 때 까지 걸리는 시간을 최소화 한다.

3. 사용 가능도의 향상 : 시스템을 이용하고 싶을 때 언제든지 이용할 수 있는 가를 나타냄.  >> 고장시 복구 시간등의 개념또한 가진다.

4. 신뢰도의 향상 : 시스템이 주어진 문제를 얼마나 정확하게 해결할 수 있는지를 나타냄

## OS의 역할

OS는 HW를 활용할 수 있게 SW나 펌웨어로 만들어져 있는 시스템 프로그램이다. OS는 **컴퓨터의 능력을 사용자가 잘 활용할 수 있게 하고**, **하드웨어가 높은 성능을 발휘할 수 있게 관리하는 역할**을 한다. 운영체제의 역할은 다음과 같다.

1. 부팅
2. 저장 매체 관리 (Disk)
3. UI
4. 컴퓨터 자원관리
5. 파일 관리
6. 프로세스 관리

## OS의 작동방식

 

### 멀티프로그래밍 :

컴퓨터에는 CPU와 다양한 I/O 디바이스들이 존재하는데 CPU에는 단 하나의 프로그램 밖에 올라가지 않는다. 만약 해결중이던 프로세스가 I/O 대기 상태면 CPU는 그동안 놀게 된다. 따라서 *메모리* 에 여러 프로세스들을 올려두고 I/O대기 상태가 되면 다음 Job으로 넘어가 최대한 CPU의 대기상태를 제거 하는 방식이다.

하지만 이 방식에도 단점이 있는데 **사용자가 현재 진행중인 작업에 대해 관여할 수 없다는 것이다**. 더 중요한 일이 급하게 해결해야 한다 하더라도 자발적 양보에 의존하기 때문에 I/O를 하지 않는 작업이라면 기다릴 수 밖에 없다. 이 문제는 Job Scheduling으로도 해결할 수 없다.

 -------
 
 수행해야하는 작업 1과 작업 2가 있다면
 작업 1은 CPU를 사용한 후 I/O장치를 사용하고,
 작업 2은 CPU만을 사용하는 작업일 때

 작업 1이 먼저 수행되면서 CPU를 사용하고 I/O를 사용하는 동안 CPU는 놀고있음에도 불구하고 작업 2는 메모리에 올라가있지 않기 때문에 작업 1이 끝나기 전에는 시작할 수 없다. 그래서 **멀티프로그래밍!!**
 

 

### 타임 셰어링:

시간 공유방식은 멀티 프로그래밍에서 확장된 방식이다. 멀티 태스킹(Multi-tasking)이라고 부르기도 한다. 

일괄 처리 시스템에서는 하나의 잡이 끝날때까지 다른 작업이 CPU를 사용할 수 없는 문제가 있다. 그**래서 CPU가 스케쥴링을 통해 작업들을 빠르게 스위칭 하면서 동시에 프로그램이 작동하는 것처럼 느껴지게 한다.** 멀티 태스킹을 위해 메모리에 여러 잡을 올려 놓으면 메모리가 모자라는 경우가 생길 수 있는데, 그럴 경우 스와핑을 통해 프로세스를 가상 메모리에 저장한다.

CPU의 실행 시간을 나누는 단위를 타임 슬라이스라고 한다. 일반적으로 10ms이며 모든 job은 타임 슬라이스동안 PU를 점유라고 그 시간이 끝나면 CPU를 양보한다.

 
### 운영체제는 interrupt(event)-driven 방식
인터럽트:

현대의 OS는 인터럽트 방식을 사용한다. 인터럽트란 CPU가 job을 처리하고 있을 때, I/O 디바이스 등의 장치나 예외상황이 발생하여 처리가 필요할 경우 신호를 주어 처리할 수 있도록 하는 것을 말한다. 인터럽트는 HW인터럽트, SW인터럽트 두 가지 방식으로 나뉜다.

 SW interrupt

1. S/W interrupts - trap( or exception)
      - S/W errors : 흔히 프로그래밍하면서 나올 수 있는 error ( divide by zero, stack overflows...)
      - 운영체제 services 들에 대한 요청 -> System Call


 HW interrupt




 https://been2.tistory.com/19