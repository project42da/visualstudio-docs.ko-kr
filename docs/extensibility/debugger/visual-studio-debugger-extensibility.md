---
title: Visual Studio 디버거 확장성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], Debugging SDK
- Debugging SDK
ms.assetid: c088b6a2-c3ad-446b-830d-9c6f41b2934b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e5bb01c093fda068dfbc7dfa705914a8bdef4d2b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="visual-studio-debugger-extensibility"></a>Visual Studio 디버거 확장성
Visual Studio에는 프로그램에서 버그를 추적 하기 위한 강력 하 고 사용 하기 쉬운 도구를 제공 하는 완전 한 대화형 소스 코드 디버거 포함 되어 있습니다. 디버거는 완전히 지원 Visual Basic, C#, C/c + + 및 JavaScript에 있습니다. 그러나는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], 즉에서 사용할 수는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkId=214453), 같은 다양 한 기능으로는 디버거에서 다른 프로그래밍 언어를 지원할 수 있습니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버거는 공용 프런트 엔드 (즉, 사용자 인터페이스) 인 게 디버깅 중인 언어에는 디버깅 구성 요소는 합니다. 새 언어에 대 한 하 여 지원에 필요한 모든는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버거를 디버그 엔진 (DE)와 같은 필요한 백 엔드 구성 요소를 만드는 것입니다. 정답입니다는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 제공 합니다.  
  
 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 모두에 대 한 자세한 포함 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 새 DE를 만드는 데 필요한 요소입니다. 또한, 샘플 및 자습서를 시작 하는 데 도움이 되는 됩니다.  
  
 디버깅 지원 언어 프로젝트 시스템의 종단 간 샘플을 참조 하십시오.는 [IronPython 샘플](http://msdn.microsoft.com/en-us/4c41695c-12c1-4670-b43b-d8d84c9e4089)합니다.  
  
 다음 섹션에서는 디버거를 사용 하 여 확장 하는 방법에 설명 된 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [시작](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)  
 에서는 작업을 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅 SDK를 설치 하는 방법 및을 제공 합니다.  
  
 [사용자 지정 디버그 엔진 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 DE 분리를 DE에 대 한 프로그램을 준비 하 고에서 사용자 지정 DE 프로세스에 설명 합니다.  
  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)  
 식 계산기를 작성 해야 하는지 여부를 설명 합니다.  
  
 [디버그 엔진 구현 전략 선택](../../extensibility/debugger/choosing-a-debug-engine-implementation-strategy.md)  
 프로그램 DE를 구현 하는 방법을 설명 합니다.  
  
 [참조](../../extensibility/debugger/reference/reference-visual-studio-debugging-apis.md)  
 문서는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅 API입니다.  
  
 [샘플](../../extensibility/debugger/visual-studio-debugging-samples.md)  
 공용 언어 런타임 식 계산기 샘플 및 디버그 엔진 샘플에 대 한 링크를 포함합니다.
