---
title: "IDebugSourceServerModule | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugSourceServerModule 인터페이스"
ms.assetid: 38213060-451d-46e6-8b4a-efc123e01a2c
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugSourceServerModule
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

PDB 파일에 포함 된 원본 서버의 정보를 나타냅니다.  
  
## 구문  
  
```  
IDebugSourceServerModule : IUnknown  
```  
  
## 구현자 참고 사항  
 이 인터페이스 디버거 엔진으로 구현 되 고 디버거에서 UI를 사용 합니다.  
  
## 메서드  
 다음 표에서 메서드를 `IDebugSourceServerModule`.  
  
|메서드|설명|  
|---------|--------|  
|[GetSourceServerData](../../../extensibility/debugger/reference/idebugsourceservermodule-getsourceserverdata.md)|원본 서버 정보 배열을 검색 합니다.|  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll