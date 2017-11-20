---
title: "상황에 맞는 코드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], contexts
ms.assetid: 65e4d37a-086b-426e-9394-a3534967fd59
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 92d6ed317bcf6ceead42db850ee61969409eb136
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="code-context"></a>코드 컨텍스트
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 을 디버깅 하는 **코드 컨텍스트**:  
  
-   디버그 엔진 (DE)에 알려진 코드에서 위치에 대 한 추상화를 제공 합니다. 대부분 런타임 아키텍처에 대 한 현재 코드 컨텍스트 생각할 수 있습니다 프로그램의 명령 스트림에 주소로 합니다. 여기서 코드 지침으로 표시 될 수 있습니다, 일반적인 언어에 대 한 코드 컨텍스트를 다른 방법으로 표시할 수 있습니다.  
  
-   디버깅 중인 프로그램의 실행 스트림 내의 현재 위치를 설명 합니다.  
  
-   프로그램이 중단점에서 중지 된 경우에 존재 합니다.  
  
-   관련된 문서 컨텍스트를 있습니다.  
  
-   에 의해 구현 된 [IDebugCodeContext2](../../extensibility/debugger/reference/idebugcodecontext2.md) 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 컨텍스트](../../extensibility/debugger/document-context.md)   
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)