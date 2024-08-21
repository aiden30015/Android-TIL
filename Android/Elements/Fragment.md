# 안드로이드 Fragment 요약

안드로이드에서 Fragment는 앱 UI를 구성하는 재사용 가능한 컴포넌트입니다. Activity 내에서 부분적인 화면을 담당하며, 하나의 Activity 내에서 여러 Fragment를 결합해 복잡한 UI를 구성할 수 있습니다. Fragment는 생명주기 관리가 중요하며, Activity의 생명주기에 종속되지만 자체적으로도 `onCreate()`, `onStart()`, `onResume()`, `onPause()`, `onStop()`, `onDestroyView()` 등의 생명주기 메서드를 가집니다.

## 주요 특징 및 사용 예

1. **재사용 가능성**  
   Fragment는 UI 요소를 재사용할 수 있게 해줍니다. 같은 Fragment를 여러 Activity나 다른 Fragment에서 사용할 수 있습니다.

2. **유연한 UI 구성**  
   화면 크기에 따라 다른 레이아웃을 제공할 수 있습니다. 예를 들어, 태블릿에서는 두 개의 Fragment를 한 화면에 보여주고, 스마트폰에서는 하나씩 순차적으로 보여줄 수 있습니다.

3. **생명주기 관리**  
   Fragment는 Activity와 생명주기를 공유하지만, 자체적인 생명주기 메서드를 통해 더 정밀한 제어가 가능합니다. Activity가 파괴되거나 재생성될 때 Fragment도 함께 처리됩니다.

4. **FragmentManager와 FragmentTransaction**  
   Fragment를 추가, 제거, 교체할 때 `FragmentManager`와 `FragmentTransaction`을 사용합니다. `replace()`, `add()`, `remove()` 등의 메서드를 통해 Fragment의 전환을 관리할 수 있습니다.

5. **백스택 관리**  
   Fragment 간 전환 시 백스택을 관리하여 뒤로 가기 버튼으로 이전 상태로 돌아갈 수 있게 할 수 있습니다.

6. **호환성**  
   구버전의 안드로이드에서도 Fragment를 사용할 수 있도록 `androidx.fragment.app.Fragment`를 포함한 AndroidX 라이브러리를 사용할 수 있습니다.

---

Fragment는 복잡한 UI를 효과적으로 구성하고 관리할 수 있게 해주는 강력한 도구로, 안드로이드 앱 개발에서 필수적인 역할을 합니다.
