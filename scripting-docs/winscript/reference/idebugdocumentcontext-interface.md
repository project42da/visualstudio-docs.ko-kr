---
title: "IDebugDocumentContext 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugDocumentContext 인터페이스"
ms.assetid: 665ee08a-5c6a-4ab1-ab93-de376acc9a74
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugDocumentContext 인터페이스
디버깅 중인 문서 중 일부는 추상 표현을 제공 합니다.  텍스트 문서에서이 표현을 문자 위치 범위 구성 됩니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugDocumentContext` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugDocumentContext::GetDocument](../../winscript/reference/idebugdocumentcontext-getdocument.md)|이 컨텍스트를 포함 하는 문서를 반환 합니다.|  
|[IDebugDocumentContext::EnumCodeContexts](../../winscript/reference/idebugdocumentcontext-enumcodecontexts.md)|이 문서 컨텍스트와 연관 된 코드 컨텍스트를 열거 합니다.|