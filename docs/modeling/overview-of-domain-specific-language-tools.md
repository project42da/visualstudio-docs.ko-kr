---
title: "도메인 특정 언어 도구 개요 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language
ms.assetid: 50d93ea2-8c88-4522-853b-40ab194953db
caps.latest.revision: "54"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 20d4222f96958a730c563ff9bc84b2b5d0b08538
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="overview-of-domain-specific-language-tools"></a>도메인별 언어 도구 개요
도메인 특정 언어 도구 (DSL 도구)에서 호스팅되는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]사용 도메인 특정 언어를 디자인 하 고 다음 사용자의 언어를 기반으로 하는 모델을 만들 수 있어야 하는 모든 항목을 생성 합니다.  
  
 DSL 도구에는 다음과 같은 도구가 포함 됩니다.  
  
-   도메인 특정 언어 개발을 시작할 수 있도록 다른 솔루션 템플릿을 사용 하는 프로젝트 마법사.  
  
-   만들고 도메인 특정 언어 정의 편집 하기 위한 그래픽 디자이너.  
  
-   도메인 특정 언어 정의 올바른 형식을 갖추도록 이며 문제가 있는 경우 오류 및 경고를 표시 하도록 하는 유효성 검사 엔진입니다.  
  
-   도메인 특정 언어 정의 입력으로 사용 하 고 출력으로 소스 코드를 생성 하는 코드 생성기입니다.  
  
## <a name="the-dsl-tools-solution"></a>DSL Tools 솔루션  
 도메인 특정 디자이너 마법사에는 다음과 같은 솔루션 템플릿을 제공합니다.  
  
-   작업 흐름  
  
-   클래스 다이어그램  
  
-   최소 언어  
  
-   구성 요소 모델  
  
-   최소한의 WPF  
  
-   최소 Windows.Forms  
  
-   DSL 라이브러리  
  
 자세한 내용은 참조 [도메인별 언어 솔루션 템플릿을 선택](../modeling/choosing-a-domain-specific-language-solution-template.md)합니다.  
  
 마법사는 만듭니다는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 다음 프로젝트가 포함 된 솔루션:  
  
-   Dsl  
  
     도메인 특정 언어와 편집 및 처리 도구를 정의 하는 Dsl 프로젝트입니다.  
  
-   **DslPackage**  
  
     DslPackage 프로젝트 언어 도구와 통합 하는 방법을 결정 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
## <a name="the-dsl-tools-graphical-interface"></a>DSL Tools 그래픽 인터페이스  
 DSL 도구 그래픽 인터페이스를 사용 하 여 도메인 특정 언어에 요소 및 관계를 추가할 수 있습니다. 요소를 추가 하면 셰이프에 매핑하여, 색, 사용자 지정 및 데코레이터를 추가 하 여 모양을 정의할 수 있습니다. 도구 상자에는 요소를 추가할 수도 있습니다.  
  
## <a name="validation-in-dsl-tools"></a>DSL 도구에서 유효성 검사  
 Dsl 한 수준의 코드 생성에 대 한 도메인 모델은 기본 요구 사항을 충족 하는지 확인 하려면 유효성 검사를 제공 합니다. 일반적으로 고유한 도메인 특정 언어를 만들 때 비즈니스 논리 규칙을 표현 하 여 고유한 유효성 검사를 추가 합니다. 사용자 지정 유효성 검사에 대 한 자세한 내용은 참조 [도메인 특정 언어의 유효성 검사](../modeling/validation-in-a-domain-specific-language.md)합니다.  
  
 확인 하는 도메인 특정 언어 종종 때 디자인 하는 것이 좋습니다. 도메인 특정 언어 유효성 검사 오류가 있으면 소스 코드를 생성할 수 없습니다. 소스 코드는 템플릿에서 생성 하는 과정을 클릭 하 여 수행 됩니다 **모든 템플릿 변형** 솔루션 탐색기의 도구 모음에서입니다. 언어 정의 수정할 때마다 또한 해야 **모든 템플릿 변형**합니다. 자세한 내용은 참조 [하는 방법: 도메인 특정 언어 솔루션을 만들어](../modeling/how-to-create-a-domain-specific-language-solution.md)합니다.  
  
## <a name="customization-of-dsl-tools"></a>DSL 도구의 사용자 지정  
 모델의 동작을 구체화 하 고 해당 언어를 통해 제약 조건을 정의 하는 추가 코드를 제공할 수 있습니다. 필요한 경우 텍스트 템플릿을 수정 하 여 중요 한 변경 가능 합니다.  
  
## <a name="distributing-your-dsl-solution"></a>DSL 솔루션 배포  
 에 호스트 된 패키지를 생성 하는 DSL 도구 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 패키지는 도구 상자, DSL 탐색기 및 도메인 특정 언어를 사용 하 여 모델을 만들 수 있도록 하는 기타 UI 요소를 표시 합니다.  
  
 빌드하고 DSL 도구 솔루션에서 실행 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 두 번째 인스턴스 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 도메인 특정 언어 언어의 사용자에 게 표시 하는 방법을 보여 줍니다. 모든 항목이 올바르게 작동 하는지 확인 한 후 배포할 수는 `.vsix` DslPackage 프로젝트의 빌드 폴더에서 확인할 수 있는 파일입니다. DSL으로 설치 하려면이 파일을 사용할 수 있습니다는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 다른 컴퓨터에서 확장 합니다.  자세한 내용은 참조 [도메인별 언어 솔루션 배포](../modeling/deploying-domain-specific-language-solutions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [실험적 인스턴스](../extensibility/the-experimental-instance.md)   
 [도메인 특정 언어 도구 용어집](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)