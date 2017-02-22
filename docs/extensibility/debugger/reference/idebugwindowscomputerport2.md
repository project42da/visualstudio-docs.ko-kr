---
title: "IDebugWindowsComputerPort2 | Microsoft Docs"
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
  - "IDebugWindowsComputerPort2 인터페이스"
ms.assetid: 25f327b8-0303-4268-88d1-74df630436aa
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugWindowsComputerPort2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

대상 컴퓨터에 대 한 정보를 쿼리할 수 있습니다.  
  
## 구문  
  
```  
IDebugWindowsComputerPort2 : IUnknown  
```  
  
## 구현자 참고 사항  
 이 인터페이스는 디버그 세션 관리자의 포트 개체에 의해 구현 됩니다.  
  
## 메서드  
 다음 표에서 메서드를 `IDebugWindowsComputerPort2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetComputerInfo](../../../extensibility/debugger/reference/idebugwindowscomputerport2-getcomputerinfo.md)|컴퓨터에 대 한 정보를 검색 합니다. 디버거를 실행 합니다.|  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll