---
title: "IDebugProgramDestroyEventFlags2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugProgramDestroyEventFlags2 인터페이스"
ms.assetid: d384ff71-dc71-40b9-a871-801f8b6a3418
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgramDestroyEventFlags2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진의 기본 동작을 재정의할 수 있습니다 해당 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 디버그 세션을 종료 하면 UI입니다.  
  
## 구문  
  
```  
IDebugProgramDestroyEventFlags2 : IUnknown  
```  
  
## 구현자 참고 사항  
 이 인터페이스는 디버그 엔진에서 구현 됩니다.  수도 있습니다 생성 하는 프로세스의 수명 여러 프로그램을 파괴 하는 호스트에 대 한 유용 합니다.  
  
## 메서드  
 다음 표에서 메서드를 `IDebugProgramDestroyEventFlags2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)|프로그램 검색 플래그를 파괴 하십시오.|  
  
## 설명  
 기본적으로는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] UI 인 디자인 모드로 돌아가 프로그램 프로그램을 모두 보낸 후에 이벤트를 파괴 하십시오.  이 인터페이스는 디버그 엔진을 해당 동작을 변경할 수 있습니다.  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll