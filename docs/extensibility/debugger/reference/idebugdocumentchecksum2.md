---
title: "IDebugDocumentChecksum2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugDocumentChecksum2 인터페이스"
ms.assetid: 6d22fa94-21aa-46cb-b5b5-32a6399ebb20
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IDebugDocumentChecksum2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 문서에 대 한 체크섬을 나타냅니다 및 체크섬 구성 요소 간에 전달 하면 됩니다.  
  
## 구문  
  
```  
IDebugDocumentChecksum2 : IUnknown  
```  
  
## 구현자 참고 사항  
 노출 하는 구성 요소에서이 인터페이스를 구현할 수 있는 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 인터페이스입니다.  그러나 심볼 파일 \(\*.pdb\)에 포함 된 검사 값이 IDE로 다시 전달 하는 소스를 찾을 때 사용 되는 수 있도록 디버그 엔진에서 인라인으로 구현 됩니다.  
  
## 메서드  
 다음 표에서 메서드를 `IDebugDocumentChecksum2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetChecksumAndAlgorithmId](../../../extensibility/debugger/reference/idebugdocumentchecksum2-getchecksumandalgorithmid.md)|최대 바이트 수를 지정 된 문서 체크섬 및 알고리즘 식별자를 검색 합니다.|  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll