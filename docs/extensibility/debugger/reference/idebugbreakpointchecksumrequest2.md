---
title: "IDebugBreakpointChecksumRequest2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugBreakpointChecksumRequest2 인터페이스"
ms.assetid: 9cfdbca5-052c-48e9-8411-e2e9e4065d00
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IDebugBreakpointChecksumRequest2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

문서 중단점 요청에 대 한 체크섬을 나타냅니다.  
  
## 구문  
  
```  
IDebugBreakpointChecksumRequest2 : IUnknown  
```  
  
## 구현자 참고 사항  
 로 구현 된는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 패키지를 디버깅 및 디버깅 엔진으로 사용.  
  
## 메서드  
 다음 표에서 메서드를 `IDebugBreakpointChecksumRequest2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetChecksum](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-getchecksum.md)|문서 검사를 사용 하는 체크섬 알고리즘의 고유 식별자를 제공 중단점 요청에 대 한 검색 합니다.|  
|[IsChecksumEnabled](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-ischecksumenabled.md)|이 문서에 대 한 체크섬을 사용할 수 있는지 확인 합니다.|  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll