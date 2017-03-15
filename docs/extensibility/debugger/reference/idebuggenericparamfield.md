---
title: "IDebugGenericParamField | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugGenericParamField 인터페이스"
ms.assetid: ba24f499-5ba7-4c67-83e6-923229b52327
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# IDebugGenericParamField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

관리 되는 코드가 제네릭 형식에 대 한 매개 변수를 나타냅니다.  
  
## 구문  
  
```  
IDebugGenericParamField : IDebugField  
```  
  
## 구현자 참고 사항  
 제네릭에 대 한 지원을 사용 합니다.  
  
## 메서드  
 메서드 외에 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[ConstraintCount](../../../extensibility/debugger/reference/idebuggenericparamfield-constraintcount.md)|이 제네릭 매개 변수와 관련 된 제약 조건을 반환 합니다.|  
|[GetConstraints](../../../extensibility/debugger/reference/idebuggenericparamfield-getconstraints.md)|이 제네릭 매개 변수와 관련 된 제약 조건으로 검색 합니다.|  
|[GetFlags](../../../extensibility/debugger/reference/idebuggenericparamfield-getflags.md)|제네릭 매개 변수의 플래그를 검색합니다.|  
|[GetIndex](../../../extensibility/debugger/reference/idebuggenericparamfield-getindex.md)|이 제네릭 매개 변수의 인덱스를 검색합니다.|  
|[GetNameOfFormalParam](../../../extensibility/debugger/reference/idebuggenericparamfield-getnameofformalparam.md)|이 제네릭 매개 변수의 이름을 검색합니다.|  
|[GetOwner](../../../extensibility/debugger/reference/idebuggenericparamfield-getowner.md)|이 제네릭 매개 변수의 형식 또는 메서드의 소유자를 검색합니다.|  
  
## 요구 사항  
 헤더: Sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll