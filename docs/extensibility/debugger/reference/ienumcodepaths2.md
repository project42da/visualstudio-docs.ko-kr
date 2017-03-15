---
title: "IEnumCodePaths2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumCodePaths2"
helpviewer_keywords: 
  - "IEnumCodePaths2 인터페이스"
ms.assetid: 17ec9f9e-dc06-4532-b5db-da52efcc8630
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IEnumCodePaths2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 코드 경로의 목록을 나타냅니다.  
  
## 구문  
  
```  
IEnumCodePaths2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 코드 경로 목록을 표시 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md) 이 인터페이스를 가져올 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IEnumCodePaths2`.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumcodepaths2-next.md)|코드 경로 열거 시퀀스에서 지정 된 수를 검색합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumcodepaths2-skip.md)|코드 경로 열거 시퀀스에서 지정 된 수를 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumcodepaths2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumcodepaths2-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumcodepaths2-getcount.md)|코드 경로 수를의 열거자를 가져옵니다.|  
  
## 설명  
 분기 지점 또는 함수 호출을 프로그램에서 코드 경로 나타냅니다.  코드 경로 목록을 통해 코드 실행에 소요 된 경로 나타냅니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)