---
title: "IDebugProperty2::SetValueAsReference | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProperty2::SetValueAsReference"
helpviewer_keywords: 
  - "IDebugProperty2::SetValueAsReference 메서드"
ms.assetid: 341b1b89-4ab8-4e1c-abe2-fb955df5c6b0
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugProperty2::SetValueAsReference
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 속성의 값을 지정한 참조의 값으로 설정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetValueAsReference(  
   IDebugReference2** rgpArgs,  
   DWORD              dwArgCount,  
   IDebugReference2*  pValue,  
   DWORD              dwTimeout  
);  
```  
  
```c#  
int SetValueAsReference(  
   IDebugReference2[] rgpArgs,  
   uint               dwArgCount,  
   IDebugReference2   pValue,  
   uint               dwTimeout  
);  
```  
  
#### 매개 변수  
 `rgpArgs`  
 \[in\] 관리 되는 코드 속성 setter에 전달할 인수 배열입니다.  속성 setter는 인수를 사용 하지 않는 경우 또는이 경우 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 와 같은 속성 setter에 개체를 참조 하지 않습니다 `rgpArgs` null 값 이어야 합니다.  이 매개 변수는 일반적으로 null 값입니다.  
  
 `dwArgCount`  
 \[in\] 인수 개수는 `rgpArgs` 배열입니다.  
  
 `pValue`  
 \[in\] 참조 형식으로 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 개체를 사용 하 여이 속성을 설정 하는 값입니다.  
  
 `dwTimeout`  
 \[in\] 시간 값을 밀리초 단위로 설정 하는 데 있습니다.  기본값은입니다 `INFINITE`.  이 모든 가능한 평가 소요 기간을 영향을 줍니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 다음 중 하나 일반적으로 오류 코드를 반환합니다.  
  
|오류|설명|  
|--------|--------|  
|`E_SETVALUEASREFERENCE_NOTSUPPORTED`|값에 대 한 참조를 설정할 수 없습니다.|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|이 속성에는 메서드를 참조 하는 대로 값을 설정할 수 없습니다.|  
|`E_SETVALUE_VALUE_IS_READONLY`|값은 읽기 전용 이며 설정할 수 없습니다.|  
|`E_NOTIMPL`|메서드가 구현되지 않았습니다.|  
  
## 참고 항목  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)