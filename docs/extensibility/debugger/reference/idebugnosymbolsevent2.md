---
title: "IDebugNoSymbolsEvent2 | Microsoft Docs"
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
  - "IDebugNoSymbolsEvent2 인터페이스"
ms.assetid: f6fb6388-47f6-4385-9ad5-95d62f9a7592
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugNoSymbolsEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

신호를 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 디버거에서 기호 시작된 실행 파일을 찾을 수 있는 사용자에 게 경고 하는 사용자 인터페이스입니다.  
  
## 구문  
  
```  
IDebugNoSymbolsEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진으로 구현 되 고 소비는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 디버거 UI입니다.  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll