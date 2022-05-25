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

####Testing Your System
먼저 sbt(스칼라 빌드 도구)가 설치되어 있는지 확인하십시오. [sbt](http://www.scala-sbt.org/release/docs/Getting-Started/Setup.html)에서 자세한 내용을 참조하십시오. 

    $ sbt run

이것은 항상 숫자 42(일명 0x2a)를 출력하는 간단한 블록(`Hello`)을 생성하고 테스트합니다. 블록이 테스트 케이스를 통과했음을 나타내기 전에 출력의 마지막 라인(sbt에서)에 `[success]`가 표시되고 라인에 `PASSED`가 표시되어야 합니다. 처음으로 이 작업을 수행하는 경우 sbt는 적절한 버전의 Chisel3, Chisel Testers harness 및 Scala를 자동으로 다운로드하고 캐시합니다(보통 `~/.ivy2`에 있음).

Completing the Tutorials
------------------------

To learn Chisel, we recommend learning by example and just trying things out.
To help with this, we have produced exercises with circuits (`src/main/scala/problems`) and their
 associated test harnesses (`src/test/scala/problems`) which have clearly
marked places to complete their functionality and simple test cases. You can
compare your work with our sample solutions in (`src/main/scala/solutions`) and (`src/test/scala/solutions`).  This 
hierarchical organization and separation of circuits and tests is a good practice and we encourage you to understand it
and use it in the future.  Typically when you work on a problem you will have two open editor windows (vi, emacs, IDE, 
etc) one to edit the circuit and the other to edit the tests.

To speed things up, we will keep sbt running. To get started:

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
