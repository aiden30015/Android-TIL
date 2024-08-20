# RecyclerView

## 개념

AdapterView의 종류중 하나로, 가장 보편적으로 사용된다  
같은 형태의 아이템을, 내용만 바꿔 여러번 사용해야될때 사용  
아이템 개수보다 적은, 화면에 맞는 일정 개수의 ViewHolder만 생성하여, 재활용함!

## ListView와의 차이점

ListView의 단점

1. 스크롤시 버벅임. findViewById 메소드 사용으로 비용이 상당히 많이듬
2. 기본 애니메이션 지원이 없음. 커스터마이징 해야함
3. 오직 수직 스크롤만 가능  
   단점들을 보완한것이 RecyclerView

## 준비물

**ViewHolder**,**Adapter**,**LayoutManger**가 필요하다.

### ViewHolder란?

화면에 표시될 아이템 뷰를 저장하는 객체!  
ViewHolder가 데이터를 가지고 있고, 그 데이터가 화면에 나타난다.  
스크롤을 내릴 때 이미 만들어진 ViewHolder가 존재한다면 데이터만 바인딩시켜서 사용하게 된다.

### Adapter

Adapter는 리스트를 화면에 표시하기 위해서 아이템 단위로 View로 생성을 해서 RecyclerView에 바인딩 시키는 작업을 하는 객체이다.  
개발자가 직접 작성하여 RecyclerView에 연결시킨다.

### LayoutManager

아이템뷰를 원하는 방향(수직,수평,격자)형태로 배치할 수 있다.

## 사용법

1.Activity에 RecyclerView 추가

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".ui.favorite.MyFragment">
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/recyclerView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>
</LinearLayout>
```

2.RecyclerView에 item View 레이아웃 추가

```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_marginVertical="10dp"
    android:layout_marginHorizontal="20dp"
    android:layout_width="match_parent"
    android:layout_height="wrap_content">
  <ImageView
            android:id="@+id/imageView"
            android:layout_width="100dp"
            android:layout_height="100dp"
            android:layout_margin="10dp"/>
	<TextView
						android:id="@+id/textView"
		        android:layout_width="wrap_content"
		        android:layout_height="wrap_content"
		        android:textSize="32sp"/>
</LinearLayout>
```

3.RecyclerView Adapter,ViewHolder 구현

```kt
class FavoriteRecyclerAdapter(val items: ArrayList<Favorite>): RecyclerView.Adapter<FavoriteRecyclerAdapter.ViewHolder>(){

    interface OnItemClickListener{
        fun OnItemClick(url:String)
    }

    var itemClickListener:OnItemClickListener?=null

    inner class ViewHolder(val binding: FavoriteRowBinding):RecyclerView.ViewHolder(binding.root){
        init {
            binding.root.setOnClickListener {
                itemClickListener?.OnItemClick(items[adapterPosition].url)
            }
        }
    }

    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): ViewHolder {
        val view = FavoriteRowBinding.inflate(LayoutInflater.from(parent.context), parent, false)
        return ViewHolder(view)
    }

    override fun onBindViewHolder(holder: ViewHolder, position: Int) {
        holder.binding.apply {
            textView.text = items[position].fName
            imageView.setImageResource(items[position].id1)
        }
    }

    override fun getItemCount(): Int {
        return items.size
    }
}
```

4. RecyclerView의 Adapter와 LayoutManager 지정

```kt
adapter = FavoriteRecyclerAdapter(items)
binding.recyclerView.apply {
      addItemDecoration(decoration)
      layoutManager = LinearLayoutManager(requireContext(),RecyclerView.VERTICAL, false)
      adapter = this@MyFragment.adapter
}
```
