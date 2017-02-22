---
title: "문서 컨텍스트 | Microsoft Docs"
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
  - "디버깅 [디버깅 SDK] 컨텍스트"
ms.assetid: 8e8b5702-5c16-4988-953d-69dd807d8b84
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# 문서 컨텍스트
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅은  **문서 컨텍스트**:  
  
-   소스 파일의 위치를 나타냅니다.  여기서 원본 파일이 없을 수 있습니다 언어의 문서 컨텍스트 일반적으로 런타임 환경에 의해 생성 되는 문서에서 위치를 식별 합니다.  예를 들어, 스크립팅 엔진이 스크립트에서 문서를 생성할 수 있습니다.  자세한 내용은  [문서 위치](../../extensibility/debugger/document-position.md).  
  
-   코드 컨텍스트를 해당 소스 문서의 위치를 설명 합니다.  설명서 컨텍스트로, 컴파일러나 인터프리터에 의해 생성 된 정보를 사용 하 여 코드 컨텍스트를 기호 처리기에 매핑합니다.  
  
-   에 의해 구현 되는  [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md) 인터페이스입니다.  
  
## 참고 항목  
 [코드 컨텍스트](../../extensibility/debugger/code-context.md)   
 [기호 공급자](../../extensibility/debugger/symbol-provider.md)   
 [기호 공급자 인터페이스](../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)