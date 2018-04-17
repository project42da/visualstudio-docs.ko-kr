---
title: 중단점 (Visual Studio SDK) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- breakpoints
ms.assetid: acfcabed-9f2f-436c-ad18-7ca2f45d631b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 42f2efe2785f508bedb104e495309ed40fc6ce39
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="breakpoints-visual-studio-sdk"></a>중단점 (Visual Studio SDK)
중단점의 세 가지: 보류 중, 바인딩, 및 오류입니다.  
  
 **중단점 보류 중인 A:**  
  
-   하나 이상의 응용 프로그램에 하나 이상의 코드 컨텍스트에 중단점을 바인딩할 때 필요한 모든 정보를 포함 하는 추상화가입니다. 때마다 원인 로드 하는 코드 디버깅 중인 프로그램의 디버그 엔진 확인 모든 보류 중인 중단점을 바인딩할 수 있으면 참조 합니다.  
  
     자체는 주로 보류 중단점 되지 코드로 하지만 대신 수집 바인딩하고 생성 하는 바인딩된 모든 중단점을 포함 되었다고 합니다.  
  
-   로 표시 됩니다는 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) 인터페이스입니다.  
  
 **바인딩된 중단점:**  
  
-   중단점에 대 한 추상화 연결 하거나 단일 코드 컨텍스트에 바인딩할 합니다. 바인딩된 각 중단점은 보류 중인 중단점에 대 한 응답으로 생성 됩니다. 그러나 보류 중인 중단점 수, 바인딩된 중단점이 여러 개를 생성 했습니다.  
  
     코드 언로드될 때 바인딩된 중단점이 바인딩되지 않은 되며 삭제 수 있습니다.  
  
-   로 표시 됩니다는 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) 인터페이스입니다.  
  
 **오류 중단점:**  
  
-   보류 중인 중단점 코드 컨텍스트를 바인딩할 도중에 오류가 설명 하기 위한 추상화가입니다. 오류 중단점 중 하나가 오류 중단점 식 자체 또는 위치에 설명합니다. 자세한 내용은 참조 [바인딩 중단점](../../extensibility/debugger/binding-breakpoints.md)합니다.  
  
     중단점 오류는 오류 또는 경고 중 수 있습니다.  
  
-   로 표시 됩니다는 [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램](../../extensibility/debugger/programs.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [코드 컨텍스트](../../extensibility/debugger/code-context.md)   
 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)