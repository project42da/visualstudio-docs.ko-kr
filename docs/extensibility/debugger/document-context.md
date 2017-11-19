---
title: "컨텍스트 문서 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], contexts
ms.assetid: 8e8b5702-5c16-4988-953d-69dd807d8b84
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5a38d0ad28ad01b9e106cf06127b934dedfe5bba
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="document-context"></a>문서 컨텍스트
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 을 디버깅 하는 **문서 컨텍스트**:  
  
-   소스 파일의 위치를 나타냅니다. 소스 파일을 있을 수 없는 언어에 대 한 문서 컨텍스트는 런타임 환경에서 일반적으로 생성 된 문서에서 위치를 식별 합니다. 예를 들어 스크립팅 엔진 스크립트에서 문서를 생성할 수 있습니다. 자세한 내용은 참조 [문서 위치](../../extensibility/debugger/document-position.md)합니다.  
  
-   코드 컨텍스트에 해당 하는 소스 문서의 위치를 설명 합니다. 기호 처리기 코드 컨텍스트를 컴파일러 또는 인터프리터에서 생성 된 정보를 사용 하 여 설명서 컨텍스트를 매핑합니다.  
  
-   에 의해 구현 된 [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md) 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드 컨텍스트](../../extensibility/debugger/code-context.md)   
 [기호 공급자](../../extensibility/debugger/symbol-provider.md)   
 [기호 공급자 인터페이스](../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)