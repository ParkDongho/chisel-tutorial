Chisel Tutorials (Release branch)
================

These are the tutorials for [Chisel](https://github.com/ucb-bar/chisel3).

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

치즐을 배우려면 예제를 통해 배우고 시도해 보는 것이 좋습니다. 이를 돕기 위해 회로(`src/main/scala/problems`) 및 관련 test_harnesses(`src/test/scala/problems`)를 사용하여 기능과 간단한 테스트 사례를 완료할 위치를 명확하게 표시한 연습을 만들었습니다. (`src/main/scala/solutions`) 및 (`src/test/scala/solutions`)에서 샘플 솔루션과 작업을 비교할 수 있습니다. 이 계층적 구성과 회로와 테스트의 분리는 좋은 관행이며 이해하고 미래에 사용하는 것이 좋습니다. 일반적으로 문제에 대해 작업할 때 두 개의 열린 편집기 창(`vi, emacs, IDE 등`)이 하나는 회로를 편집하고 다른 하나는 테스트를 편집하기 위한 것입니다.

속도를 높이기 위해 sbt를 계속 실행합니다. 시작하려면:

    $ sbt

#### Mux2
This should already work. Try

    > test:runMain problems.Launcher Mux2
    
Note that `Mux2` is defined in `Mux4.scala`.

#### Mux4
You can instantiate a module with `val foo = Module(new Bar())`

    > test:runMain problems.Launcher Mux4

#### Counter
You can conditionally update a value without a mux by using `when (cond) { foo := bar }`

    > test:runMain problems.Launcher Counter

#### Vending Machine

    > test:runMain problems.Launcher VendingMachine

#### Memo
The type of memory that's inferred is based on how you handle the read and
write enables. This is pretty much the same as how Xilinx and Altera infer
memories.

    > test:runMain problems.Launcher Memo

#### Mul

    > test:runMain problems.Launcher Mul

#### RealGCD

    > test:runMain problems.Launcher RealGCD


To check that all of your solutions are correct:

    $ ./run-problem.sh all


To run all of our reference solutions:

    $ ./run-solution.sh all

Note: ./run-problem.sh, ./run-solution.sh, ./run-examples.sh are convenience scripts to invoke tests

Learning More Chisel
--------------------
In addition to the problems and the solutions, we have also provided some
examples of more complex circuits (`src/main/scala/examples`) and (`src/test/scala/examples`). You should take a 
look at the source and test them out:

    $ ./run-examples.sh all

The [wiki](https://github.com/ucb-bar/chisel-tutorial/wiki/) attached to this repo contains more information on working with Chisel.
Additional documentation may be found on the chisel3 repo
[wiki](https://github.com/ucb-bar/chisel3/wiki/)
and the
[documentation](https://chisel.eecs.berkeley.edu/documentation.html)
section of the [website](https://chisel.eecs.berkeley.edu/).

Fixes/Updates
-------------
If you wish to submit pull requests for changes to this repo, plus check out the master branch, and make your pull requests against that branch.
