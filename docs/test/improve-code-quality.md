---
title: "코드 품질 향상"
ms.custom: na
ms.date: 02/17/2017
ms.reviewer: na
ms.suite: na
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: na
ms.topic: article
helpviewer_keywords:
- Visual Studio ALM
- team-based development
ms.assetid: 73baa961-c21f-43fe-bb92-3f59ae9b5945
caps.latest.revision: 39
ms.author: douge
manager: douge
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a42f5a30375192c89c9984e40ba0104da98d7253
ms.openlocfilehash: 2fa87621ed76fb93a9e92d558be5519d783274c5
ms.lasthandoff: 03/07/2017

---
# <a name="improve-code-quality"></a>코드 품질 향상
코드 품질이란 무엇입니까? 좋은 코드를 만들 때는 정확성, 유지 관리의 편의성 및 정교함까지 고려해야 합니다. 어떻게 정의하든 Visual Studio 테스트 도구를 사용하면 사용자와 팀이 수준 높은 코드를 개발하고 유지할 수 있습니다.  
  
 **Requirements**  
  
-   이 단원에서 설명하는 도구와 기능 중 일부는 Visual Studio에서 일반적으로 사용할 수 없는 Visual Studio의 특정 버전에서만 사용할 수 있습니다. 이러한 도구와 기능에 대한 설명서에서 특정 버전 요구 사항을 보여 줍니다.  
  
## <a name="in-this-section"></a>단원 내용  
 다음 표에서는 일반적인 작업에 대한 설명과 해당 작업을 성공적으로 완료하는 방법에 대한 자세한 내용을 볼 수 있는 링크를 보여 줍니다.  
  
|||  
|-|-|  
|[코드 단위 테스트](../test/unit-test-your-code.md)|테스트 탐색기를 사용하면 개발 연습에서 단위 테스트를 쉽게 통합할 수 있습니다. Microsoft 단위 테스트 프레임워크를 사용하거나 여러 타사 및 공개 소스 프레임워크 중 하나를 사용할 수 있습니다.|  
|[Visual Studio를 사용한 Live Unit Testing](../test/live-unit-testing.md)|Live Unit Testing은 자동으로 백그라운드에서 단위 테스트를 실행하고 Visual Studio 코드 편집기의 코드 검사 및 테스트 결과를 그래픽으로 표시합니다.|  
|[응용 프로그램 품질 분석](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md)|정족 코드 분석 도구는 C++ 및 관리 코드에서 디자인, 사용, 유지 관리 및 스타일 문제를 검색합니다. 이러한 문제의 대부분은 표준 테스트 환경에서 재현하기 어려운 버그를 일으킬 수 있습니다.|  
|[관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)|코드 메트릭은 개발자가 개발 중인 코드에 대해 더 정확히 파악할 수 있도록 하는 소프트웨어 측정 방법입니다. 메트릭에는 함수 및 클래스에 대한 유지 관리 인덱스, 함수의 순환 복잡성(Cyclomatic Complexity), 클래스의 상속 깊이, 클래스 간의 결합 양을 포함합니다.|  
  
## <a name="related-scenarios"></a>관련 시나리오  
 [애플리케이션 수명 주기 관리에 Visual Studio 및 Team Foundation Server 도입](assetId:///7ae9182f-4762-4bd3-b238-39ce987932e5)  
 Visual Studio Team Foundation에 익숙하지 않은 경우 팀 개발 환경에서 이 제품을 사용하여 생산성을 높이고 응용 프로그램 개발 시 발생할 수 있는 위험을 줄이는 방법에 대해 알아보십시오.  
  
 [아키텍처 분석 및 모델링](../modeling/analyze-and-model-your-architecture.md)  
 [!INCLUDE[vsPreExt](../test/includes/vspreext_md.md)]을 사용하여 소프트웨어를 디자인하는 데 따르는 어려움과 복잡성을 관리할 수 있습니다. [!INCLUDE[vsPreShort](../test/includes/vspreshort_md.md)]에서는 응용 프로그램을 현재 상태 및 사용자가 원하는 상태로 시각적으로 모델링할 수 있습니다. 응용 프로그램의 논리 모델을 실제 모델에 매핑하는 동시에 시각화할 수 있도록 다이어그램을 만들고 유지 관리할 수 있습니다. 이렇게 하면 "디자인 중"인 소프트웨어에 대해 변경, 유효성 검사 및 분석을 수행할 수 있습니다.  
  
 [응용 프로그램 테스트](https://www.visualstudio.com/docs/test/overview)  
 [!INCLUDE[vsPreShort](../test/includes/vspreshort_md.md)] 및 [!INCLUDE[vsUltShort](../test/includes/vsultshort_md.md)]을 사용하여 테스트 수명 주기 전체에서 생산성을 높일 수 있습니다. [!INCLUDE[vsPreShort](../test/includes/vspreshort_md.md)] 또는 [!INCLUDE[vsUltShort](../test/includes/vsultshort_md.md)]에서는 테스트 관련 활동을 계획할 수 있습니다. 수동 테스트와 자동화된 테스트를 모두 만들고, 관리하고, 편집하고, 실행할 수 있습니다. 또한 계획에 따라 테스트 진행률을 검토할 수 있습니다.  
  
 [PreEmptive Protection - Dotfuscator로 응용 프로그램 보호](../ide/dotfuscator/index.md)  
 무료 Dotfuscator Community Edition을 사용하여 거래 비밀 및 기타 IP(지적 재산권)를 보호하고, 불법 복제 및 위조를 줄이고, 변조 및 무단 디버깅으로부터 보호하는 데 도움을 얻을 수 있습니다.  Dotfuscator는 추가적인 프로그래밍이나 소스 코드 액세스 없이도 컴파일된 어셈블리를 보호하고 강화합니다.
  
 [응용 프로그램 빌드](https://www.visualstudio.com/docs/build/overview)  
 [!INCLUDE[esprbuild](../test/includes/esprbuild_md.md)]를 사용하여 코드에 대해 자동화된 빌드를 만들고 관리할 수 있습니다. [!INCLUDE[esprbuild](../test/includes/esprbuild_md.md)]를 사용하면 서버를 만들어 빌드를 배포할 수 있습니다. 또한 빌드 추세를 분석할 수 있습니다.  
  
 [Visual Studio Online 또는 Team Foundation Server를 사용하여 작업 추적](https://www.visualstudio.com/docs/work/overview)  
 [!INCLUDE[vstsTfsLong](../test/includes/vststfslong_md.md)]를 사용하여 프로젝트에서 활성 프로세스, 공식 프로세스 또는 이러한 프로세스의 변형 중에서 무엇을 사용할지를 계획하고 추적할 수 있습니다. 프로젝트를 계획하고, 계획에 대한 진행률을 추적하고, 필요한 사항을 조정하면 위험을 줄이고, 원하지 않는 상황을 방지하고, 프로젝트 비용을 관리할 수 있습니다.

