---
title: "IDebugReference2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugReference2"
helpviewer_keywords: 
  - "IDebugReference2 인터페이스"
ms.assetid: 3cfed312-f532-4bce-84a5-1677c14567d7
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugReference2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 스택 프레임 속성 또는 일부 다른 속성에 대 한 참조를 나타냅니다.  
  
> [!NOTE]
>  `IDebugReference2`나중에 사용할 수 있도록 및 모든 해당 메서드 반환에 대 한 예약 되어 `E_NOTIMPL`.  
  
## 구문  
  
```  
IDebugReference2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE의 특정 종류의 값에 대 한 참조를 나타내는 데이 인터페이스를 구현 합니다.  예를 들어, 값은 메모리 또는 레지스터 및 해당 값 목록을 표시 하는 데 사용 되는 메모리 컨텍스트 식 계산의 결과 숫자 값을 수 있습니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [GetReference](../../../extensibility/debugger/reference/idebugproperty2-getreference.md) 이 인터페이스를 가져올 수 있습니다.  [GetParent](../../../extensibility/debugger/reference/idebugreference2-getparent.md)및 [GetDerivedMostReference](../../../extensibility/debugger/reference/idebugreference2-getderivedmostreference.md) 또한이 인터페이스를 반환 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugReference2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)|가져옵니다는 [DEBUG\_REFERENCE\_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) 이 참조를 설명 하는 구조입니다.|  
|[SetValueAsString](../../../extensibility/debugger/reference/idebugreference2-setvalueasstring.md)|이 참조는 문자열에서 값을 설정합니다.|  
|[SetValueAsReference](../../../extensibility/debugger/reference/idebugreference2-setvalueasreference.md)|이 참조 다른 참조의 값을 설정 합니다.|  
|[EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)|이 참조의 자식을 열거합니다.|  
|[GetParent](../../../extensibility/debugger/reference/idebugreference2-getparent.md)|이 참조의 부모를 가져옵니다.|  
|[GetDerivedMostReference](../../../extensibility/debugger/reference/idebugreference2-getderivedmostreference.md)|이 참조의 가장 많이 파생 참조를 가져옵니다.|  
|[GetMemoryBytes](../../../extensibility/debugger/reference/idebugreference2-getmemorybytes.md)|이 참조를 참조 하는 메모리 \(바이트\)를 가져옵니다.|  
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)|메모리 컨텍스트에서를이 대 한이 참조를 가져옵니다.|  
|[GetSize](../../../extensibility/debugger/reference/idebugreference2-getsize.md)|이 참조 바이트 단위로 크기를 가져옵니다.|  
|[SetReferenceType](../../../extensibility/debugger/reference/idebugreference2-setreferencetype.md)|이 참조 형식이 설정 됩니다.|  
|[비교](../../../extensibility/debugger/reference/idebugreference2-compare.md)|이에 다른이 참조를 비교합니다.|  
  
## 설명  
  
> [!NOTE]
>  "속성"이이 사용 해당 멤버 변수를 클래스의 의미와 일치 하지 않습니다을 `IDebugReference2` 와 같은 엔터티를 나타낼 수 있습니다.  
  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)속성을 나타내는 동안 `IDebugReference2` 일반적으로 디버깅 중인 프로그램의 개체를 참조 하는 속성에 대 한 참조를 나타냅니다.  
  
 명명 되지 않은 인스턴스에 대 한 참조를 참조 하는 속성 개체의 명명 된 인스턴스를 참조 하는 속성에 대 한 참조 간의 주요 차이점이입니다.  예를 들어, 속성에 의해 프로그램의 힙 개체를 참조할 수 있습니다 `"a.b"`.  다른 속성과 같은 개체 이름으로 참조할 수 있습니다 `"c.d"`.  이 속성을 참조 하는 방법 필요로 하는 `"a.b"` 또는 `"c.d"` 범위에서 수 있습니다.  이 같은 개체에 대 한 참조 이름이 됩니다. 해당 개체에 대 한 메모리 잘못으로 개체를 참조할 수 있습니다.  
  
 `IDebugProperty2` 인터페이스 간주할 수 있습니다 값 이름, 종류, 및 주소를 사용 합니다.  `IDebugReference2`, 다른 손으로, 중 고 주소 유형으로 생각할 수 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG\_REFERENCE\_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [GetReference](../../../extensibility/debugger/reference/idebugproperty2-getreference.md)