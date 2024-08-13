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
