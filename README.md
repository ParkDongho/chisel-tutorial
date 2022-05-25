Chisel Tutorials (Release branch)
================

[Chisel](https://github.com/ucb-bar/chisel3)에 대한 튜토리얼입니다.

Chisel은 고도로 매개변수화된 생성기와 계층화된 도메인별 하드웨어 언어를 사용하여 고급 하드웨어 설계를 지원하는 UC Berkeley에서 개발된 오픈 소스 하드웨어 구성 언어입니다.


Getting the Repo
----------------

    $ git clone https://github.com/ucb-bar/chisel-tutorial.git
    $ cd chisel-tutorial
    $ git fetch origin
    $ git checkout release


Executing Chisel
----------------

#### Testing Your System
먼저 sbt(스칼라 빌드 도구)가 설치되어 있는지 확인하십시오. [sbt](http://www.scala-sbt.org/release/docs/Getting-Started/Setup.html)에서 자세한 내용을 참조하십시오. 

    $ sbt run

이것은 항상 숫자 42(일명 0x2a)를 출력하는 간단한 블록(`Hello`)을 생성하고 테스트합니다. 블록이 테스트 케이스를 통과했음을 나타내기 전에 출력의 마지막 라인(sbt에서)에 `[success]`가 표시되고 라인에 `PASSED`가 표시되어야 합니다. 처음으로 이 작업을 수행하는 경우 sbt는 적절한 버전의 Chisel3, Chisel Testers harness 및 Scala를 자동으로 다운로드하고 캐시합니다(보통 `~/.ivy2`에 있음).

Completing the Tutorials
------------------------

Chisel을 배우려면 예제를 통해 배우고 시도해 보는 것이 좋습니다. 이를 돕기 위해 회로(`src/main/scala/problems`) 및 관련 test_harnesses(`src/test/scala/problems`)를 사용하여 기능과 간단한 테스트 사례를 완료할 위치를 명확하게 표시한 연습을 만들었습니다. (`src/main/scala/solutions`) 및 (`src/test/scala/solutions`)에서 샘플 솔루션과 작업을 비교할 수 있습니다. 이 계층적 구성과 회로와 테스트의 분리는 좋은 관행이며 이해하고 미래에 사용하는 것이 좋습니다. 일반적으로 문제에 대해 작업할 때 두 개의 열린 편집기 창(`vi, emacs, IDE 등`)이 하나는 회로를 편집하고 다른 하나는 테스트를 편집하기 위한 것입니다.

속도를 높이기 위해 sbt를 계속 실행합니다. 시작하려면:

    $ sbt

#### Mux2
This should already work. Try

    > test:runMain problems.Launcher Mux2
    
`Mux2`는 `Mux4.scala`에 정의되어 있습니다.

#### Mux4
`val foo = Module(new Bar())`로 모듈을 인스턴스화할 수 있습니다.

    > test:runMain problems.Launcher Mux4

#### Counter
`when (cond) { foo := bar }`를 사용하여 mux 없이 값을 조건부로 업데이트할 수 있습니다.

    > test:runMain problems.Launcher Counter

#### Vending Machine

    > test:runMain problems.Launcher VendingMachine

#### Memo
유추되는 메모리 유형은 읽기 및 쓰기 활성화를 처리하는 방법을 기반으로 합니다. 이것은 Xilinx와 Altera가 메모리를 추론하는 방법과 거의 동일합니다.

    > test:runMain problems.Launcher Memo

#### Mul

    > test:runMain problems.Launcher Mul

#### RealGCD

    > test:runMain problems.Launcher RealGCD


모든 솔루션이 올바른지 확인하려면:

    $ ./run-problem.sh all


모든 참조 솔루션을 실행하려면:

    $ ./run-solution.sh all

참고: ./run-problem.sh, ./run-solution.sh, ./run-examples.sh는 테스트를 호출하는 편의 스크립트입니다.

Learning More Chisel
--------------------
문제와 솔루션 외에도 더 복잡한 회로(`src/main/scala/examples`) 및 (`src/test/scala/examples`)의 몇 가지 예도 제공했습니다. 소스를 살펴보고 테스트해야 합니다.

    $ ./run-examples.sh all

이 저장소에 첨부된 [wiki](https://github.com/ucb-bar/chisel-tutorial/wiki/)에는 Chisel 작업에 대한 자세한 정보가 포함되어 있습니다.
추가 문서는 chisel3 repo에서 찾을 수 있습니다.
[위키](https://github.com/ucb-bar/chisel3/wiki/)
및 [웹사이트](https://chisel.eecs.berkeley.edu/)의 [문서](https://chisel.eecs.berkeley.edu/documentation.html) 섹션.

Fixes/Updates
-------------
이 리포지토리에 대한 변경 사항에 대한 풀 리퀘스트를 제출하고 마스터 브랜치를 확인하고 해당 브랜치에 대해 풀 리퀘스트를 수행하십시오.
