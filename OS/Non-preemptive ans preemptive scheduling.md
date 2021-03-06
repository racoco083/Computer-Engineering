## 선점과 비선점 스케줄링

선점 스케줄링의 경우에는 I/O요청, I/O응답, Interrupt발생, 작업완료 등의 상황에서 스케줄링이 일어날 수 있다. 
하지만 비선점 스케줄링의 경우 프로세스가 스스로 CPU를 놓아주는 시점(작업이 완료되는 시점)에만 스케줄링이 일어난다.. 

## 선점 스케줄링 종류

* SRT(Shortest Remaining Time) 스케줄링: 짧은 시간 순서대로 프로세스를 수행한다. 남은 처리 시간이 더 짧은 프로세스가 Ready 큐에 들어오면 그 프로세스가 바로 선점됨. 아래에 소개할 SJF의 선점 버전이라고 할 수 있다.
* 라운드로빈(Round-Robin)스케줄링: 각 프로세스는 같은 크기의 CPU 시간을 할당 받고 선입선출에 의해 행된다. 할당시간이 너무 크면 선입선출과 다를 바가 없어지고, 너무 작으면 오버헤드가 너무 커진다.
* 다단계 큐(Multi-level Queue) 스케줄링: Ready큐를 여러 개 사용하는 기법. 각각의 큐는 자신의 스케줄링 알고리즘을 수행하며, 큐와 큐 사이에도 우선순위를 부여한다.
* 다단계 피드백 큐 스케줄링: 다단계 큐와 비슷하나 프로세스들이 큐를 이동할 수 있다.

## 비선점 스케줄링 종류

* HRN(Highest response ratio next) 스케줄링: 긴 작업과 짧은 작업간의 지나친 불평등을 어느 정도 보완한 기법. 수행시간의 길이와 대기 시간을 모두 고려해 우선순위를 정한다.
* SJF(Shortest Job First) 스케줄링: 큐 안에 있는 프로세스 중 수행시간이 짧은 것을 먼저 수행. 평균 대기 시간을 감소시킨다.
* 우선순위(priority) 스케줄링: 프로세스에게 우선순위를 정적, 혹은 동적으로 부여하여 우선순위가 높은 순서대로 처리한다. 동적으로 부여할 경우, 구현이 복잡하고 오버헤드가 많다는 단점이 있으나, 시스템의 응답속도를 증가시킨다.
* 기한부(Deadline) 스케줄링: 작업을 명시된 시간이나 기한 내에 완료하도록 계획.
* FIFO 스케줄링: 프로세스들은 Ready큐에 도착한 순서대로 CPU를 할당 받는다. 작업 완료 시간을 예측하기 매우 용이하다. 하지만 덜 중요한 작업이 중요한 작업을 기다리게 할 수도 있다.

## 디스패처(dispatcher)

![image](https://user-images.githubusercontent.com/21019088/56453814-9187b880-6382-11e9-87ac-793646ed7124.png)

## Reference
https://preamtree.tistory.com/19
