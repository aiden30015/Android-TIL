# FrameLayout

## 정의

**FrameLayout은 그 안에 포함되어 있는 자식뷰들을 차례대로 중첩시켜 나타내는 레이아웃**을 말합니다.  
다른 레이아웃 뷰그룹 처럼 내부에 포함된 여러 자식뷰들을 여기저기 배치시켜 화면을 구성하는 용도로 사용하는 것이
아니고 주로 **겹쳐진 뷰들 중에서 사용자에 의해 선택되어지는 뷰 하나만 화면에 보이거나 아니면 감추어지도록  
구현하는데 사용**됩니다. 이를 구현하기 위해서 자식뷰들은 보통 visibility 속성과 함께 사용됩니다.

## 속성

1. foregroundGravity : 전경 이미지의 중력방향을 지정합니다. (ex, foregroundGravity="center")

2. measureAllChildren : 해당 속성이 true일 경우 자식 뷰의 visibility 속성에 "gone"이 적용되어도 "invisible"이 적용된 것처럼 자식 뷰의 공간을 유지하도록 합니다. (ex, measureAllChildren="true")

## 예제

```kt
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent" >

    <TextView
        android:id="@+id/textView1"
        android:layout_width="320dp"
        android:layout_height="320dp"
        android:visibility="visible"
        android:layout_gravity="center"
        android:gravity="center"
        android:text="첫번째뷰"
        android:textSize="32dp"
        android:background="#FFAB40" />

    <TextView
        android:id="@+id/textView2"
        android:layout_width="320dp"
        android:layout_height="320dp"
        android:visibility="invisible"
        android:layout_gravity="center"
        android:gravity="center"
        android:text="두번째뷰"
        android:textSize="32dp"
        android:background="#40C4FF" />

    <Button
        android:id="@+id/button"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_gravity="bottom"
        android:padding="20dp"
        android:text="화면전환 버튼"
        android:textSize="24dp"
        android:textColor="@color/white"
        android:backgroundTint="#C62828"/>
</FrameLayout>
```

화면 전환 버튼 누르면 자식 뷰가 직접적으로 바뀌는게 아니라  
visibility 속성을 활용하여 전환되는듯한 효과를 줌
