---
title: 디버거에서 확장에 대 한 로드맵 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], roadmap
- Debugging SDK, roadmap
ms.assetid: 1f4096a8-f7aa-4dfa-84e1-6d59263e70bb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 46c5a8a995644d6876457836674152eb3b3ccad7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="roadmap-for-extending-the-debugger"></a>디버거에서 확장에 대 한 로드맵
확장 하기 위한 가이드 및 참조 정보를 제공 하는이 설명서는 [!INCLUDE[vs_current_short](../../code-quality/includes/vs_current_short_md.md)] 으로 디버거는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 설명서 디버깅 샘플과 포괄적인 참조는 디버거를 사용자 지정 하는 일반적인 방법을 보여 주는 몇 가지 대표 시나리오에 포함 됩니다.  
  
 컴파일러 및 출력에는 제품에서 디버깅을 구현 하기 위해 필요한를 결정 합니다. 하는 경우 컴파일러:  
  
-   Windows 기본 운영 체제를 대상으로 하 고 작성 한 합니다. PDB 파일에 통합 된 네이티브 코드 디버그 엔진 (DE) 프로그램을 디버깅할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. DE 또는 식 계산기를 구현할 필요가 없습니다. 식 계산기는 c + + 프로그래밍 언어의 구문에 대 한 기록 됩니다.  
  
-   Microsoft에도 통합 된 관리 코드 디버그 엔진 DE, 프로그램을 디버깅할 수를 MSIL (intermediate language)에서 출력을 생성 합니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 따라서 식 계산기를 구현만 필요 합니다. 샘플 식 계산기는 하기 위해 제공 됩니다. 자세한 내용은 다음 항목을 참조하세요.  
  
     [식 계산](../../extensibility/debugger/expression-evaluation-visual-studio-debugging-sdk.md)  
  
     [식 계산](../../extensibility/debugger/evaluating-expressions.md)  
  
     [식 계산 컨텍스트](../../extensibility/debugger/expression-evaluation-context.md)  
  
     [중단 모드에서 식 계산](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
     [공용 언어 런타임 식 계산기 작성](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)  
  
-   소유 운영 체제나 다른 몇 가지 런타임 환경에서는 대상을 직접 DE 작성 해야 했습니다. ATL COM을 사용 하 여 간단한 DE 만드는 자습서가 제공 됩니다. 자세한 내용은 다음 항목을 참조하세요.  
  
     [사용자 지정 디버그 엔진 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
  
     [자습서: ATL COM을 사용 하 여 디버그 엔진을 구축](http://msdn.microsoft.com/en-us/9097b71e-1fe7-48f7-bc00-009e25940c24)  
  
     [포트 공급자 구현](../../extensibility/debugger/implementing-a-port-supplier.md)  
  
     [샘플](../../extensibility/debugger/visual-studio-debugging-samples.md)  
  
## <a name="see-also"></a>참고 항목  
 [시작](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)