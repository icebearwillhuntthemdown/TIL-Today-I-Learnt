# Colors

## 기본 컬러 테마
- 안드로이드 버전에 따라 달라진다.
- 접근 방식: `android:color="@android:color/name_the_color"`
```xml
<item android:color="@android:color/black"/>
<item android:color="@android:color/holo_blue_bright_"/>
```

## 커스텀 컬러 테마
- 원하는 색에 이름을 붙여 저장해놓고 사용할 수 있다.
- 접근 방식: `android:color=@color/name_the_color"`
```xml
values/color.xml
<?xml version="1.0" encoding="utf-8">
<resources>
    <color name="60%_black">#99000000</color>
    <color name="20%_red">#33FF0000</color>
</resources>
```

### 색상 코드
`\#AARRGGBB`

- 알파(투명도) 값
    * 100% — FF
    * 95% — F2
    * 90% — E6
    * 85% — D9
    * 80% — CC
    * 75% — BF
    * 70% — B3
    * 65% — A6
    * 60% — 99
    * 55% — 8C
    * 50% — 80
    * 45% — 73
    * 40% — 66
    * 35% — 59
    * 30% — 4D
    * 25% — 40
    * 20% — 33
    * 15% — 26
    * 10% — 1A
    * 5% — 0D
    * 0% — 00

## 상태에 따른 색상 변경 
- 뷰의 상태에 따라 색상이 변경되도록 지정할 수 있다.
```xml
res/color/my_color.xml
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:color="@color/white"/> <!-- 기본 색상 -->
    <item android:state_enabled="false" android:color="@color/red"/> <!-- disabled 상태일 때의 색상 -->
</selector>
```
