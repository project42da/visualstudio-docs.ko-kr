---
title: "IDebugDocumentContext 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentContext interface
ms.assetid: 665ee08a-5c6a-4ab1-ab93-de376acc9a74
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 432fbe9de5b1ab19c64ae1b9eeee36f3b1156d06
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumentcontext-interface"></a>IDebugDocumentContext 인터페이스
디버깅 중인 문서 부분의 추상적 표현을 제공 합니다. 텍스트 문서에 대 한이 표현은 문자 위치 범위의 구성 됩니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IDebugDocumentContext` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugDocumentContext::GetDocument](../../winscript/reference/idebugdocumentcontext-getdocument.md)|이 컨텍스트를 포함 하는 문서를 반환 합니다.|  
|[IDebugDocumentContext::EnumCodeContexts](../../winscript/reference/idebugdocumentcontext-enumcodecontexts.md)|이 문서 컨텍스트와 연결 된 코드 컨텍스트를 열거 합니다.|