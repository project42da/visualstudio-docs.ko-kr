---
title: "잠금 동작에 주석 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_Releases_nonreentrant_lock_"
  - "_Lock_kind_mutex_"
  - "_Lock_kind_critical_section_"
  - "_Acquires_lock_"
  - "_Releases_lock_"
  - "_Has_lock_kind_"
  - "_Releases_exclusive_lock_"
  - "_Post_same_lock_"
  - "_Requires_exclusive_lock_held_"
  - "_Requires_shared_lock_held_"
  - "_Lock_kind_semaphore_"
  - "_Requires_lock_held_"
  - "_Acquires_exclusive_lock_"
  - "_Create_lock_level_"
  - "_Acquires_nonreentrant_lock_"
  - "_Releases_shared_lock_"
  - "_Has_lock_level_"
  - "_Lock_kind_spin_lock_"
  - "_Requires_lock_not_held_"
  - "_Acquires_shared_lock_"
  - "_Requires_no_locks_held_"
  - "_Lock_level_order_"
  - "_Lock_kind_event_"
ms.assetid: 07769c25-9b97-4ab7-b175-d1c450308d7a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 잠금 동작에 주석 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다중 스레드 프로그램에서 동시성 버그를 방지 하려면, 항상 적절한 잠금 분야를 따르고 SAL 주석을 사용 합니다.  
  
 동시성 버그는 명확하지 않기 때문에 재생산, 진단 및 디버그 하기가 굉장히 어렵습니다.  스레드 인터리빙에 대한 추론이 가장 어렵고, 몇 스레드보다 많은 스레드를 가지는 코드 본문을 디자인할 때 응용할 수 없게 됩니다.  따라서, 다중 스레드 프로그램에서 잠금 분야를 따르는 것이 좋습니다.  예를 들어, 여러 잠금을 확보하는 동안 잠금 순서를 따르는것은 교착 상태를 방지 하는데 도움이 되고, 공유 리소스에 엑세스 하기 전에 적절한 보호 잠금을 획득하는 것은 경합 상태를 방지할 수 있습니다.  
  
 불행하게도, 겉보기에 간단한 잠금 규칙은 실제로 수행하기 매우 어려울 수 있습니다.  오늘날의 프로그래밍 언어와 컴파일러의 근본적인 한계는 직접적으로 사양 및 동시성 요구 사항 분석을 지원하지 않습니다.  프로그래머는 잠금을 사용하는 방법에 대한 의도를 표현하기 위해 비공식 코드 주석에 의존 해야 합니다.  
  
 동시성 SAL 주석은 책임 잠금, 데이터 가디언 쉽, 잠금 순서 계층 구조 및 예상 되는 다른 잠금 동작과 같은 잠금 부작용을 지정할 수 있도록 설계 되었습니다.  명시적 암시적 규칙을 만들면, SAL 동시성 주석은 코드가 잠금 규칙을 사용하는 방법을 문서화하는 일관된 방법을 제공 합니다.  또한 동시성 주석은 경합 상태, 교착 상태, 일치 하지 않는 동기화 작업 및 다른 미묘한 동시성 오류를 찾기 위한 코드 분석 도구의 기능을 향상시킵니다.  
  
## 일반 지침  
 주석을 사용하여 구현 \(호출 수신자\)과 클라이언트 \(호출자\) 사이의 함수 정의에 의해 지정된 계약을 명시할 수 있고, 나아가 분석을 개선해주는 프로그램의 불변 및 다른 속성 들을 나타낼 수 있습니다.  
  
 SAL은 임계 영역, 뮤텍스, 스핀 잠금 및 기타 리소스 개체와 같은 다양한 종류의 기본 잠금을 지원합니다.  다양한 동시성 주석이 잠금 식을 매개 변수로 사용합니다.  규칙에 따라, 잠금은 내부 잠금 개체의 경로 식에 따라 표시 됩니다.  
  
 일부 스레드 소유권은 규칙에 유의 합니다.  
  
-   스핀 잠금은 일반 스레드 소유권을 가진 무제한 \(uncounted\) 잠금입니다.  
  
-   뮤텍스 및 임계 영역은 분명한 스레드 소유권을 가지는 계산된 잠금입니다.  
  
-   세마포 및 이벤트는 분명 스레드가 소유권을 가지지 않은 계산된 잠금입니다.  
  
## 주석 잠금  
 다음 표는 잠금 주석들을 나열합니다.  
  
|주석|설명|  
|--------|--------|  
|`_Acquires_exclusive_lock_(expr)`|함수에 주석을 추가하고, 포스트 상태에서 함수는 `expr` 잠금 개체의 단독 잠금 수 만큼 증가함을 나타냅니다.|  
|`_Acquires_lock_(expr)`|함수에 주석을 추가하고, 포스트 상태에서 함수는 `expr` 잠금 개체의 잠금 수 만큼 증가함을 나타냅니다.|  
|`_Acquires_nonreentrant_lock_(expr)`|`expr` 잠금을 얻게 됩니다.  잠금이 이미 있으면 오류가 보고 됩니다.|  
|`_Acquires_shared_lock_(expr)`|함수에 주석을 추가하고, 포스트 상태에서 함수는 `expr` 잠금 개체의 공유 잠금 수 만큼 증가함을 나타냅니다.|  
|`_Create_lock_level_(name)`|기호 `name` 를 선언하여 `_Has_Lock_level_` 및 `_Lock_level_order_` 주석에 사용할 수 있는 잠금 수준이 되도록 하는 문입니다.|  
|`_Has_lock_kind_(kind)`|개체를 주석 처리 하여 리소스 개체의 형식 정보를 구체화합니다.  때때로 일반적인 형식은 다양한 종류의 리소스에 대해 사용되고 오버 로드 된 형식은 다양한 리소스 사이에서 의미적 요구 사항을 구분 하기에 충분하지 않습니다.  미리 정의된 `kind` 매개 변수들 입니다:<br /><br /> `_Lock_kind_mutex_`<br /> 뮤텍스에 대한 잠금 종류 ID.<br /><br /> `_Lock_kind_event_`<br /> 이벤트에 대한 잠금 종류 ID.<br /><br /> `_Lock_kind_semaphore_`<br /> 세마포에 대한 잠금 종류 ID.<br /><br /> `_Lock_kind_spin_lock_`<br /> 스핀 잠금에 대한 잠금 종류 ID.<br /><br /> `_Lock_kind_critical_section_`<br /> 임계 영역에 대한 잠금 종류 ID.|  
|`_Has_lock_level_(name)`|잠금 개체에 주석을 추가하고 `name` 잠금 수준을 부여합니다.|  
|`_Lock_level_order_(name1, name2)`|`name1` 및 `name2` 사이의 잠금 순서를 제공하는 문입니다.|  
|`_Post_same_lock_(expr1, expr2)`|함수에 주석을 추가하고, 포스트 상태에서 두 가지 잠금 상태인 `expr1` 및 `expr2` 가 동일한 잠금 개체처럼 처리됨을 나타냅니다.|  
|`_Releases_exclusive_lock_(expr)`|함수에 주석을 추가하고, 포스트 상태에서 함수는 `expr` 잠금 개체의 단독 잠금 수 만큼 감소함을 나타냅니다.|  
|`_Releases_lock_(expr)`|함수에 주석을 추가하고, 포스트 상태에서 함수는 `expr` 잠금 개체의 잠금 수 만큼 감소함을 나타냅니다.|  
|`_Releases_nonreentrant_lock_(expr)`|`expr` 잠금이 풀립니다.  현재 잠금이 홀드되지 않은 경우, 오류가 보고 됩니다.|  
|`_Releases_shared_lock_(expr)`|함수에 주석을 추가하고, 포스트 상태에서 함수는 `expr` 잠금 개체의 공유 잠금 수 만큼 감소함을 나타냅니다.|  
|`_Requires_lock_held_(expr)`|함수에 주석을 추가하고 사전에 상태에서 `expr` 개체의 잠금 횟수를 나타냅니다.|  
|`_Requires_lock_not_held_(expr)`|함수에 주석을 추가하고 사전에 상태에서 `expr` 개체의 잠금 횟수가 0임을 나타냅니다.|  
|`_Requires_no_locks_held_`|함수에 주석을 추가하고 검사기에 알려진 모든 잠금의 잠금 횟수가 0임을 나타냅니다.|  
|`_Requires_shared_lock_held_(expr)`|함수에 주석을 추가하고 사전에 상태에서 `expr` 개체의 공유 잠금 횟수를 나타냅니다.|  
|`_Requires_exclusive_lock_held_(expr)`|함수에 주석을 추가하고 사전에 상태에서 `expr` 개체의 전용 잠금 횟수를 나타냅니다.|  
  
## 노출되지 않은 잠금 개체에 대한 SAL 내장 함수  
 특정 잠금 개체들은 관련된 잠금 함수의 구현에 의해 노출되지 않습니다.  다음 표에서 이러한 노출 되지 않은 잠금 개체에서 작동하는 함수에 대한 주석을 활성화 하는 SAL 내장 변수를 나열합니다.  
  
|주석|설명|  
|--------|--------|  
|`_Global_cancel_spin_lock_`|취소 스핀 잠금을 설명합니다.|  
|`_Global_critical_region_`|중요한 영역을 설명합니다.|  
|`_Global_interlock_`|연동된 작업을 설명 합니다.|  
|`_Global_priority_region_`|우선 순위 영역을 설명 합니다.|  
  
## 공유 데이터 액세스 주석  
 다음 표에서 공유 데이터 액세스에 대한 주석을 나열합니다.  
  
|주석|설명|  
|--------|--------|  
|`_Guarded_by_(expr)`|변수를 주석처리 하고 변수가 엑세스 될 때마다 `expr` 잠금 개체의 횟수가 하나 이상임을 나타냅니다.|  
|`_Interlocked_`|변수를 주석 처리하고 `_Guarded_by_(_Global_interlock_)` 와 동일합니다.|  
|`_Interlocked_operand_`|주석 처리된 함수 매개 변수는 다양한 Interlocked 함수 중 하나의 대상 피연산자 입니다.  해당 피연산자는 특정 추가 속성이 있어야 합니다.|  
|`_Write_guarded_by_(expr)`|변수를 주석처리 하고 변수가 수정 될 때마다 `expr` 잠금 개체의 횟수가 하나 이상임을 나타냅니다.|  
  
## 참고 항목  
 [C\/C\+\+ 코드 오류를 줄이기 위한 SAL 주석 사용](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [SAL 이해](../code-quality/understanding-sal.md)   
 [함수 매개 변수 및 반환 값에 주석 지정](../code-quality/annotating-function-parameters-and-return-values.md)   
 [함수 동작에 주석 지정](../code-quality/annotating-function-behavior.md)   
 [구조체 및 클래스에 주석 지정](../code-quality/annotating-structs-and-classes.md)   
 [주석 적용 시기 및 위치 지정](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [내장 함수](../code-quality/intrinsic-functions.md)   
 [모범 사례 및 예제](../code-quality/best-practices-and-examples-sal.md)   
 [코드 분석 팀 블로그](http://go.microsoft.com/fwlink/p/?LinkId=251197)