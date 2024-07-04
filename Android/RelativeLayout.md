# RelativeLayout

RelativeLayout은 상대 뷰의 위치를 기준으로 정렬하는 레이아웃 클래스이다. 즉, 화면에 이미 출력된 특정 뷰를 기준으로 방향을 지정하여 배치한다.
각 속성에 입력하는 값은 기준이 되는 뷰의 id이다.

- android:layout_above: 기준 뷰의 위쪽에 배치
- android:layout_below: 기준 뷰의 아래쪽에 배치
- android:layout_toLeftOf : 기준 뷰의 왼쪽에 배치
- android:layout_toRightOf : 기준 뷰의 오른쪽에 배치

RelativeLayout으로 뷰 배치하기

```xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"

    <ImageView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@mipmap/ic_launcher" />
    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="HELLO" />
</RelativeLayout>
```

실행 결과

RelativeLayout은 LinearLayout처럼 자동으로 가로세로 방향으로 배치되지 않으므로 이미지 뷰 위에 버튼이 겹쳐서 나온다. 위의 예에서 버튼을 이미지 뷰 오른쪽에 배치하려면, android:layout_toRightOf 속성을 이용한다.

상대 뷰의 오른쪽에 배치

```xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"

    <ImageView
        android:id="@+id/testImage"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@mipmap/ic_launcher" />
    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="HELLO"
        android:layout_toRightOf="@+id/testImage"/>
</RelativeLayout>
```

실행 결과

맞춤 정렬하는 align 속성
위에서 이미지의 세로 크기가 버튼보다 커서 버튼이 이미지 위쪽에 맞춰졌다. 그런데 때로는 상대 뷰의 아래쪽에 맞춰야 할 수도 있다.

이처럼 상대 뷰의 어느 쪽에 맞춰서 정렬할지를 정하는 속성은 다음과 같다. 이 속성에 입력하는 값 역시 기준이 되는 뷰의 id이다.

- android:layout_alignTop : 기준 뷰와 위쪽을 맞춤
- android:layout_alignBottom : 기준 뷰와 아래쪽을 맞춤
- android:layout_alignLeft : 기준 뷰와 왼쪽을 맞춤
- android:layout_alignRight : 기준 뷰와 오른쪽을 맞춤
- -android:layout_alignBaseline : 기준 뷰와 텍스트 기준선을 맞춤
  기준 뷰의 아래쪽을 맞춰 정렬

```xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"

    <ImageView
        android:id="@+id/testImage"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@mipmap/ic_launcher" />
    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="HELLO"
        android:layout_toRightOf="@+id/testImage"
        android:layout_alignBottom="@id/testImage"/>
</RelativeLayout>
```

실행 결과

상위 레이아웃을 기준으로 맞춤 정렬하는 속성도 있다. 뷰를 부모 영역의 오른쪽 또는 아래쪽에 붙이고 싶을 때 사용하는 속성이다.

- android:layout_alignParentTop : 부모의 위쪽에 맞춤
- android:layout_alignParentBottem : 부모의 - 아래쪽에 맞춤
- android:layout_alignParentLeft : 부모의 왼쪽에 맞춤
- android:layout_alignParentRight : 부모의 오른쪽에 맞춤
- android:layout_centerHorizontal : 부모의 가로 방향 중앙에 맞춤
- android:layout_centerVertical : 부모의 세로 방향 중앙에 맞춤
- android:layout_centerInParent : 부모의 가로, 세로 중앙에 맞춤
  부모의 오른쪽에 맞춰 정렬

```xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"

    <ImageView
        android:id="@+id/testImage"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@mipmap/ic_launcher" />
    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="HELLO"
        android:layout_alignBottom="@id/testImage"
        android:layout_alignParentRight="true"/>
</RelativeLayout>
```
