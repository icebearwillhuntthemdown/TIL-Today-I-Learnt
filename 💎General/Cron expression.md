# Cron expression

특정 시간에 반복적으로 작업을 수행할 때 쓰는 일정 주기 표현식. [배치](https://limkydev.tistory.com/140)를 실행시킬 때 사용할 수 있다.
```html 
 *    *  *  *   *   *     * 
(초)  분  시  일  월  요일  (연도)
```
<br/>

## 필드
- 초 : 없는 경우도 있음. 0-59
- 분 : 0-59
- 시 : 0-23
- 일 : 0-31
- 월 : 1-12 또는 JAN-DEC
- 요일 : 0-6 또는 SUN-SAT
- 연도 : Optional. 1970-2099
<br/>

## 기호
- * : 모든 값
- ? : 특정한 값이 없음 
- - : 범위
- , : 특정 값 
- / : 시작 시간 / 반복 단위 e.g.) 0분부터 매 5분 0/5
- L : last. 일에서는 해당 월의 말일, 요일에서는 마지막 주의 해당 요일 e.g.) 5L = 마지막 주 금요일
- W : 날짜 필드에만 사용. weekday. 가장 가까운 평일 e.g.) 15W = 15일에서 가장 가까운 평일
- # : 요일 필드에만 사용. 특정 주의 특정 요일. 요일#주 e.g.) 5#3 = 매월 셋째 주 금요일


## 참고 자료
- https://zamezzz.tistory.com/197
- https://en.wikipedia.org/wiki/Cron#CRON_expression  
- https://zamezzz.tistory.com/197
- https://crontab.guru/

