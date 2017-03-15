---
title: "IDebugPortRequest2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortRequest2"
helpviewer_keywords: 
  - "IDebugPortRequest2 인터페이스"
ms.assetid: 556e610d-7c4b-44a8-965a-76a9d02b601a
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugPortRequest2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스에 포트를 설명합니다.  이 설명은 포트는 포트 공급자에 추가 하는 데 사용 됩니다.  
  
## 구문  
  
```  
IDebugPortRequest2 : IUnknown  
```  
  
## 구현자 참고 사항  
 일반적으로 Visual Studio 디버그 포트 포트 공급자 로부터 가져오는이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스에 전달 된 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) 디버그 포트를 만들 수 있습니다.  호출을 [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md) 처음에 포트를 만드는 데 사용 되는 요청을 나타내는이 인터페이스를 반환 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugPortRequest2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugportrequest2-getportname.md)|만들 포트의 이름을 가져옵니다.|  
  
## 설명  
 디버그 엔진은 일반적으로 포트 협력 업체와 상호 작용 하지 않습니다 및이 인터페이스를 사용 해야 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)   
 [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)