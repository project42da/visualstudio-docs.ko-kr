---
title: "IDebugCodeContext3 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugCodeContext3 인터페이스"
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugCodeContext3
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

확장 하 여 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 인터페이스 모듈 및 프로세스 인터페이스를 검색할 수 있도록 합니다.  
  
## 구문  
  
```  
IDebugCodeContext3 : IDebugCodeContext2  
```  
  
## 구현자 참고 사항  
 디버그 엔진으로 구현 되 고에서 사용 되는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 디버그 패키지.  
  
## 메서드  
 메서드 외에 `IDebugCodeContext2` 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetModule](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|디버그 모듈의 인터페이스에 대 한 참조를 검색합니다.|  
|[GetProcess](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|디버그 프로세스를 인터페이스에 대 한 참조를 검색합니다.|  
  
## 설명  
 이것은 일반적으로 구현 될 수 없는 선택적 인터페이스입니다.  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll