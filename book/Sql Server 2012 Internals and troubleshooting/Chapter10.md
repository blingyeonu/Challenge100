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
  
  * 링크 참고 - 
  [Perfmon_For_SQLSERVER](https://github.com/blingyeonu/Challenge100/blob/master/book/Sql%20Server%202012%20Internals%20and%20troubleshooting/SQLServer-Performance-Poster.pdf)

* PerfMon 시작하기
  * 시작 -> 모든 프로그램 -> 관리자툴에서 선택 또는 윈도우키+R 실행창 열리면 perfmon 입력
  * 실시간 또는 추적 성으로 모니터링이 가능하다.
  * 실시간 모니터링하기 Monitoring Tools>Permformance Monitor 를 클릭하면 실시간으로 서버 자원의 상태를 확인할 수 있다.
  * 서버에서 기본 제공하는 포맷 말고 사용자가 원하는 것을 선택하여 모니터링 할 수 있다.
  * Data collector sets > system 기본 모니터링 포맷을 이용가능 하며 해당 항목 우클릭 start를 클릭하면 모니터링이 시작 가능하다.
  * 기본적으로 CPU, Disk, Memory, Network 모니터링이 가능하다
  * Data collector sets > Userdefined 우클릭 New > Data Collector set을 선택하면 사용자 필요에 맞게 옵션을 선택할 수 있다.
  
* Data Collector Set Logging option
  1. Perfmonce Counter: Windows, SqlServer의 거의 모든 측면의 성능 데이터 제공
  1. Event trace data: Windows를 위한 이벤트 추적을 활용, low-level의 운영체제 추적
  1. System Configuration information: 레지스트리 키 캡쳐
  
* 유저가 원하는 옵션으로 데이터 셋을 만들면 시작, 종료, 스케줄을 지정할 수 있다. 스케줄을 활용하여 원하는 시간대 혹은 일정 사이즈까지만 수집을 하고 새로 파일을 생성하는 등의 기능을 활용할 수 있다.
* 로그 포맷은 csv, tsv, SQL, Binary 이렇게 4종류로 설정가능하다.
* 원격서버의 수집도 가능하다(실제로 원격 수집은 해보지 않았다. 나중에 테스트 해보고 싶음)

