---
title: "디버깅에 대 한 언어 서비스 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugger, language support
- language services, debugging support
ms.assetid: 7a44067f-a410-4a6a-84d2-bda5184140bc
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 955c8fd4e9499fbacfc0f97ba6112803ef1e6d4a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="language-service-support-for-debugging"></a>디버깅에 대 한 언어 서비스 지원
언어 서비스를 통해 디버거 지원 기능을 제공할 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo> 인터페이스입니다. 이러한 기능에는 중단점 유효성 검사 및 식의 목록을 제공는 **자동** 창.  
  
 그러나 해당 언어를 디버깅 하는 식 계산기가 필요 합니다. 식 계산기는 디버깅 하는 동안 값을 생성 하는 식을 계산 하는 일을 담당 합니다. CLR 식 계산기를 구현 하는 방법에 대 한 내용은 다음을 참조 하십시오.  
  
-   [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)  
  
-   [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)  
  
## <a name="compiler-output"></a>컴파일러 출력  
 컴파일러의 형식이 결정 해당 언어에 대해 디버깅을 구현 하기 위해 수행 해야 합니다. 컴파일러는 Windows 운영 체제를 대상 하.pdb 파일을 작성 하는 경우에 디버깅 엔진 Visual Studio에 통합 된 네이티브 코드와 프로그램을 디버깅할 수 있습니다. 컴파일러에서 생성 하는 Microsoft MSIL (intermediate language) 하는 경우에 디버깅 엔진도 Visual Studio에 통합 된 관리 코드와 프로그램을 디버깅할 수 있습니다. 컴파일러 전용 운영 체제 또는 다른 런타임 환경을 대상으로 하는 경우 사용자 고유의 디버깅 엔진을 작성 해야 합니다.  
  
 해당 언어에 대 한 디버깅 구현에 대 한 자세한 내용은 참조 하십시오. [시작](../../extensibility/debugger/getting-started-with-debugger-extensibility.md) Visual Studio Debugging SDK에 있습니다.