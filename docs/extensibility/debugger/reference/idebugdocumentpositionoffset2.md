---
title: "IDebugDocumentPositionOffset2 | Microsoft Docs"
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
  - "IDebugDocumentPositionOffset2 인터페이스"
ms.assetid: f1b05db3-50d8-453f-a72f-e68b239236a4
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDocumentPositionOffset2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

소스 파일에서 위치를 문자 오프셋을 나타냅니다.  
  
## 구문  
  
```  
IDebugDocumentPositionOffset2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진으로 사용 하 고 IDE에서 구현 합니다.  
  
## 메서드  
 다음 표에서 메서드를 `IDebugDocumentPositionOffset2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetRange](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2-getrange.md)|범위는 현재 문서의 위치를 검색합니다.|  
  
## 설명  
 이 같은 정보를 반환 합니다. [GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md) 에 있지만 `char` 문서의 시작 부분에서 오프셋 됩니다.  디스크에 1 차원 배열을 문자 일반적으로 반환 되는 행 및 열 정보를, 존재 하는 것 처럼이 문서를 제공 합니다.  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)