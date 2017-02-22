---
title: "IDebugPortSupplierEx2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugPortSupplierEx2 인터페이스"
ms.assetid: dae0050a-a50a-4f35-bfbd-e538f537b20f
caps.latest.revision: 4
caps.handback.revision: 4
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugPortSupplierEx2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

포트 공급자를 선택 하 고 코어 서버와 상호 작용에 대 한 지원을 제공 합니다.  
  
## 구문  
  
```  
IDebugPortSupplierEx2 : IUnknown  
```  
  
## 구현자 참고 사항  
 협력 업체 사용자 지정 포트를 사용 하는 핵심 서버를 선택할 수 있습니다이 인터페이스를 구현 합니다.  
  
## 메서드  
 다음 표에서 메서드를  **IDebugPortSupplierEx2**.  
  
|메서드|설명|  
|---------|--------|  
|[SetServer](../../../extensibility/debugger/reference/idebugportsupplierex2-setserver.md)|코어 서버 공급 업체에 대 한 포트를 설정합니다.|  
  
## 요구 사항  
 헤더: Portpriv.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)