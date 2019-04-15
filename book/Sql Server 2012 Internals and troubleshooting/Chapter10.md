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

* Perfrmon의 개요(pefmon을 통해 할 수 있는 작업)
  1. 실시간 데이터 수집
  1. 성능 데이터 시각화
  1. 성능 데이터 기록 
  1. 성능 영향의 하드웨어/소프트웨어 변화 수량화 
  1. 데이터 저장 및 내보내기
  1. 임계값에 따른 데이터 알람
  1. 다른 서버와의 데이터 비교
  1. 기본 데이터 베이스 라인 캡쳐
  
* PerfMon의 3요소 ( Monitoring tool, Data collector set, Report )

* PefMon으로 보는 자원 4요소( CPU, Disk, Network, Memory )

* Data collector sets: 문제 진단을 위해 결합된 것, LAN, System 진단, System 성능 등을 수집함. 일반적인 문제 해결 시나리오를 위한 성능카운터, 데이터 추적, 시스템 설정을 수집할 수 있다.

* Reliability Monitor: 시스템 안정성 표를 보여줌.
* 2008ver이 이전과 다른점(오래되긴했...)
  * Auto-Scaling 가능: 이전에는 특정 값이 높거나 너무 낮아서 보기가 불편해서 특정 값이 튀게 되는데 2008에서는 데이터를 좀 더 보기 쉽도록 맞춰준다.
  * Show/Hide 가능: 보고싶은 값만 보거나 필요 없는 값은 숨길 수 있다.
  
* [NewPerfmon For SQLSERVER 2012 Link] (https://github.com/blingyeonu/Challenge100/blob/master/book/Sql%20Server%202012%20Internals%20and%20troubleshooting/SQLServer-Performance-Poster.pdf)
  
