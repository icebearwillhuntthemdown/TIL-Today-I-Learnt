# Cron expression

특정 시간에 반복적으로 작업을 수행할 때 쓰는 일정 주기 표현식이다.

(초) 분 시 일 월 요일 (연도)

● * : 모든 값을 뜻합니다.
● ? : 특정한 값이 없음을 뜻합니다. 
● - : 범위를 뜻합니다. (예) 월요일에서 수요일까지는 MON-WED로 표현
● , : 특별한 값일 때만 동작 (예) 월,수,금 MON,WED,FRI 
● / : 시작시간 / 단위  (예) 0분부터 매 5분 0/5
● L : 일에서 사용하면 마지막 일, 요일에서는 마지막 요일(토요일)
● W : 가장 가까운 평일 (예) 15W는 15일에서 가장 가까운 평일 (월 ~ 금)을 찾음
● # : 몇째주의 무슨 요일을 표현 (예) 3#2 : 2번째주 수요일



출처: https://zamezzz.tistory.com/197 [배워가는블로거]
https://en.wikipedia.org/wiki/Cron#CRON_expression  
https://zamezzz.tistory.com/197

# 배치
대용량 데이터에 대한 작업을 특정 시간에 일괄 처리
https://limkydev.tistory.com/140

