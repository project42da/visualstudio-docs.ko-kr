---
title: "IDebugBinder3::FindAlias | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBinder3::FindAlias"
helpviewer_keywords: 
  - "IDebugBinder3::FindAlias 메서드"
ms.assetid: b8333701-2718-4983-8513-0875fb7cb730
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugBinder3::FindAlias
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 이름이 지정 된 별칭을 찾습니다.  이 프로그램의 모든 별칭을 검색 합니다.  
  
## 구문  
  
```cpp  
HRESULT FindAlias(  
   LPCOLESTR     pcstrName,  
   IDebugAlias** ppAlias  
);  
```  
  
```c#  
int FindAlias(  
   string          pcstrName,  
   out IDebugAlias ppAlias  
);  
```  
  
#### 매개 변수  
 `pcstrName`  
 \[in\] 찾기 위해 별칭의 이름입니다.  
  
 `ppAlias`  
 \[out\] 별칭 \(있는 경우\)를 표시 하는 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) 인터페이스입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` \(별칭이 없는 경우\) 또는 오류 코드입니다.  
  
## 설명  
 이 메서드를 호출 하기 전에 null 대상 개체 초기화. 그런 다음 나중에 별칭을 찾을 수 있는지 여부를 확인 하려면 null 값을 테스트 합니다.  
  
## 참고 항목  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)