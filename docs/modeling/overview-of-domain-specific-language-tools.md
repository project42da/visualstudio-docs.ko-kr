---
title: "도메인별 언어 도구 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도메인별 언어"
ms.assetid: 50d93ea2-8c88-4522-853b-40ab194953db
caps.latest.revision: 54
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 54
---
# 도메인별 언어 도구 개요
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

도메인 관련 언어에서 호스팅되는 도구 \(DSL 도구\), [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], let 도메인 관련 언어를 디자인 하 고 사용자의 언어를 기반으로 모델을 생성 하는 데 필요한 모든 요소를 생성 합니다.  
  
 다음 도구는 DSL 도구에 포함 되어 있습니다.  
  
-   다른 솔루션 템플릿을 사용 하 여 사용자의 도메인 관련 언어 개발을 시작 하는 데 도움이 프로젝트 마법사를.  
  
-   만들기 및 도메인 관련 언어 정의 편집 하는 그래픽 디자이너.  
  
-   도메인 관련 언어 정의 올바른 형식을 하 고 문제가 있는 경우 오류 및 경고를 표시 하는 유효성 검사 엔진입니다.  
  
-   도메인 관련 언어 정의 입력을 받고 출력으로 소스 코드를 생성 하는 코드 생성기.  
  
## DSL 도구 솔루션  
 도메인 관련 디자이너 마법사는 다음과 같은 솔루션 템플릿을 제공합니다.  
  
-   작업 흐름  
  
-   클래스 다이어그램  
  
-   최소한의 언어  
  
-   구성 요소 모델  
  
-   최소한의 WPF  
  
-   Windows.Forms 최소한의  
  
-   DSL 라이브러리  
  
 자세한 내용은 [도메인별 언어 솔루션 템플릿 선택](../modeling/choosing-a-domain-specific-language-solution-template.md)를 참조하십시오.  
  
 만듭니다 마법사는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 다음 프로젝트가 있는 솔루션:  
  
-   Dsl  
  
     Dsl 프로젝트의 편집 및 처리 도구 및 도메인 관련 언어를 정의합니다.  
  
-   **DslPackage**  
  
     DslPackage 프로젝트는 언어 도구 통합 결정 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## DSL 도구 그래픽 인터페이스  
 DSL 도구 그래픽 인터페이스를 사용 하면 요소와 관계를 도메인별 언어로 추가 수 있습니다.  요소를 추가한 후 해당 셰이프를 매핑, 색을 사용자 지정 및 decorators 추가 하 여 해당 모양을 정의할 수 있습니다.  요소를 도구 상자에 추가할 수도 있습니다.  
  
## DSL 도구에 대 한 유효성 검사  
 Dsl의 도메인 모델 코드 생성에 대 한 기본 요구 사항을 만족 하는지 확인 하는 유효성 검사를 제공 합니다.  일반적으로 자신의 도메인 관련 언어를 만들면 사용자 고유의 유효성 검사 비즈니스 논리 규칙을 표현할 수를 추가 합니다.  사용자 지정 유효성 검사에 대 한 자세한 내용은 참조 하십시오. [도메인별 언어에서 유효성 검사](../modeling/validation-in-a-domain-specific-language.md).  
  
 디자인 면에서는 도메인 관련 언어를 자주 확인 하는 것이 좋습니다.  도메인 관련 언어를 유효성 검사 오류가 있는 경우 소스 코드를 생성할 수 없습니다.  클릭 하 여 서식 파일에서 소스 코드를 생성 하는 프로세스를 수행  **모든 템플릿 변환** 솔루션 탐색기의 도구 모음에 있습니다.  언어 정의 수정할 때마다 또한 하 해야  **모든 템플릿 변환**.  자세한 내용은 [방법: 도메인별 언어 솔루션 만들기](../modeling/how-to-create-a-domain-specific-language-solution.md)를 참조하십시오.  
  
## DSL 도구 사용자 지정  
 모델의 동작을 조정 하 고 언어를 통해 제약 조건을 정의 하려면 추가 코드를 제공할 수 있습니다.  필요한 경우 중요 한 텍스트 서식 파일을 수정 하 여 변경할 수 있습니다.  
  
## DSL 솔루션 배포  
 DSL 도구에서 호스트 되는 패키지를 생성 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  패키지는 도구 상자, DSL 탐색기 및 도메인 관련 언어를 사용 하 여 모델을 만들 수 있도록 다른 UI 요소를 표시 합니다.  
  
 빌드 및 DSL 도구 솔루션을 실행 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 두 번째 인스턴스를 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 도메인 관련 언어를 언어 사용자에 게 표시 하는 방법을 보여 줍니다. 모든 제대로 작동 하는지 확인 한 다음 배포할 수 있습니다 해당 `.vsix` 파일에는 DslPackage 프로젝트의 빌드 폴더에 있습니다.  DSL로 설치 하려면이 파일을 사용할 수 있는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 확장명을 다른 컴퓨터에서.  자세한 내용은 [도메인별 언어 솔루션 배포](../modeling/deploying-domain-specific-language-solutions.md)를 참조하십시오.  
  
## 참고 항목  
 [실험적 인스턴스](../extensibility/the-experimental-instance.md)   
 [Domain\-Specific Language Tools Glossary](http://msdn.microsoft.com/ko-kr/ca5e84cb-a315-465c-be24-76aa3df276aa)