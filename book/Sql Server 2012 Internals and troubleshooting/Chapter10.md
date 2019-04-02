# 10.Viewing Server Performance with PerfMon and the PAL Tool

* 이 챕터에서 공부하는 것
  * 언제, 어떻게 Windows Perfmon을 사용하는가
  * problem counter를 사용하는 규범적인 가이드
  * PAL을 이용한 로그 분석
  * 다른 로그 분석 툴

* PerfMon은 작은 문제 포인트를 잡는데 좋은 분석 툴이다. 처음 문제를 파악할 때 매우 유용하다. 실시간 혹은 데이터 리소스 수집으로 모니터링을 할 수 있다. 문제가 발생한 뒤 분석하는 것으로도 매우 활용도가 높다. 
* PerfMon과 Sql Server가 제공하는 Profiler, extended events, DMV와 어떤점이 다른지 알아두는 것도 좋다. 또한 언제 어떻게 사용해야 유용하게 쓸 수 있는지도 알아야한다.

  * 문제의 한계점과 계측을 공급하고 설명하는 핵심
  * 정상적인 서버로 부터의 기본값을 모으는 방법
  * 분석된 수행로그를 보조해 입증을 할 수 있게하는 툴

