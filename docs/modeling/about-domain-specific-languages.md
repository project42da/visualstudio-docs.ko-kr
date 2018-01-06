---
title: "도메인 특정 언어에 대 한 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language
ms.assetid: 29e5b6f2-ece4-4f3b-ab08-5f957418702f
caps.latest.revision: "26"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 7bdd5f6f9561e3479d173a1e182ffa07649bc776
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="about-domain-specific-languages"></a>도메인별 언어 정보
C# 등 UML 한 범용 언어와 달리 도메인 특정 언어 DSL ()는 특정 문제 영역 또는 도메인의 문을 express 하도록 설계 되었습니다.  
  
 잘 알려진 Dsl 정규식과 SQL을 포함 합니다. 각 DSL은 자체 범위 외부에 있는 아이디어를 설명 하기 위해 텍스트 문자열 또는 데이터베이스 하지만 훨씬 더 안 좋은 대 한 작업을 설명 하기 위한 범용 언어 보다 훨씬 효율적입니다. 개별 산업 자신의 Dsl 갖게 됩니다. 예를 들어 telecommunications 업계에서 호출 설명 언어를 전화 통화의 상태 시퀀스를 지정 하 여 여행 업계 분위기에서 광범위 하 게 사용 DSL은 비행 예약에 설명 하는 데 사용 되는 표준입니다.  
  
 비즈니스 및 프로젝트에 특별 한 집합 dsl 설명 될 수 있는 개념을 처리 합니다. 예를 들어 이러한 응용 프로그램 중 하나에 대해 하는 DSL을 정의할 수 있습니다.  
  
-   계획의 웹 사이트의 탐색 경로입니다.  
  
-   배선 전자 부품에 대 한 다이어그램입니다.  
  
-   컨베이어 벨트와 수하물 처리 장비 공항에 대 한 네트워크입니다.  
  
 정의 하는 DSL을 디자인할 때는 *도메인 클래스* 각 도메인에 웹 페이지, 램프 또는 공항 체크 인 데스크와 같은 중요 한 개념에 대 한 합니다. 정의한 *도메인 관계* 하이퍼링크, 통신 개념을 함께 연결 된 컨베이어 벨트 등입니다.  
  
 DSL의 사용자가 만들 *모델.* 모델은 *인스턴스* DSL의 합니다. 예를 들어 특정 웹 사이트 또는 특정 장치, 또는 처리 시스템에서 특정 공항 수하물 연결은 설명 합니다.  
  
 사용자가 다이어그램 또는 Windows form으로 모델을 볼 수 있습니다. 모델 볼 수도 있습니다 XML로 저장 되는 방법은 변수인 합니다. DSL을 정의 하는 경우 각 도메인 클래스 및 관계의 인스턴스는 사용자의 화면에 표시 되는 방식을 정의할 수 있습니다. 일반적인 DSL 아이콘이 나 사각형 화살표로 연결 된 컬렉션으로 표시 됩니다.  
  
 다음 그림은 다이어그램 DSL의 작은 모델:  
  
 ![Tudor 패밀리 트리 모델](../modeling/media/tudor_familytreemodel.png "Tudor_FamilyTreeModel")  
  
## <a name="what-you-can-do-with-dsls"></a>Dsl으로 수행할 수 있습니다  
 DSL의 일반적인 응용 프로그램 코드 또는 기타 아티팩트를 생성 하는 것입니다. DSL를 정의할 때 정의할 수 있습니다 *텍스트 템플릿* DSL 모델을 읽을 하 고 텍스트 파일을 생성 합니다.  
  
 예를 들어 공항 계획을 사용 하 고 수하물 계획을 설명 하는 사용자 문서 중 일부가 뿐 아니라 처리에 대 한 소프트웨어의 일부를 생성 하는 템플릿을 작성할 수 있습니다.  
  
 DSL를 정의한 경우에 자신의 컴퓨터에 설치할 수 있는 다른 사용자에 게 배포할 수 있습니다. DSL의 사용자가 작성 하 고 모델에 편집 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
 메뉴 명령을 정의할 수 있습니다 하 고 사용자가 다른 도구 DSL 올바르게 사용 되 고 새 인스턴스를 만들 수 있도록 하는 항목 템플릿 하지 확인 하려면 유효성 검사 제약 조건을 DSL를 편집 합니다. 도구 및 기타 하나 이상의 Dsl 바꿈하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 패키지로 확장 합니다.  
  
 일반적으로 도메인 특정 언어 개발 팀이 여러 제품에 대 한 유사한 코드를 작성 해야 하는 경우 생성 됩니다. 예를 들어 수하물 처리 시스템 전문으로 하는 회사에는 있는 각 설치에 대 한 코드의 일부를 만들 수 있습니다는 수하물 트랙 DSL 정의할 수 있습니다. DSL 이점은에서 생성 된 코드를 안정적 이며 고객의 요구 사항이 변경 하는 경우 시스템 신속 하 게 업데이트할 수 있습니다 하 여 고객에 게 이해할 수 있습니다.  
  
 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]그래픽 디자이너를 직접 및 다이어그램 표기법 고유한 도메인 특정 언어를 만들고 다음 언어를 사용 하 여 각 프로젝트에 대 한 적절 한 소스 코드를 생성할 수 있습니다.  
  
## <a name="domain-specific-development"></a>도메인 특정 개발  
 도메인 특정 개발은 도메인 특정 언어를 사용 하 고 다음 언어를 구성 하 고 응용 프로그램 개발자에 게 배포 하 여 모델링할 수 있는 응용 프로그램의 부분을 식별 하는 프로세스입니다. 도메인 특정 언어를 사용 하 여 응용 프로그램에 특정 된 모델을 생성, 소스 코드를 생성 하는 모델 사용 하 고, 다음 소스 코드를 사용 하 여 응용 프로그램을 개발 하는 개발자가 제공 합니다.  
  
## <a name="aspects-of-graphical-domain-specific-development"></a>도메인 특정 그래픽을 개발 과정  
 그래픽 도메인 특정 언어는 다음과 같은 기능을 포함 해야 합니다.  
  
-   Notation  
  
-   도메인 모델  
  
-   아티팩트 생성  
  
-   Serialization  
  
-   Visual Studio와의 통합  
  
### <a name="notation"></a>Notation  
 도메인 특정 언어 요소를 쉽게 정의 하 고 확장 수를 나타내는 도메인별 구문 전체적으로 작은 집합이 있어야 합니다. 표시 된 요소를 나타내는 셰이프 및 연결선 그래픽 다이어그램 화면에서 요소 간의 관계를 나타내는 구성 됩니다. [!INCLUDE[dsl](../modeling/includes/dsl_md.md)], 셰이프를 확장 하 고 개선 도메인 특정 언어 요소를 나타내는 수입니다.  
  
### <a name="domain-model"></a>도메인 모델  
 도메인 특정 언어 요소와 일관 된 문법에 이들 간의 관계의 집합을 결합 해야 합니다. 요소 및 관계의 조합을 유효한 지 여부를 정의 해야 합니다. 예를 들어 프로그래밍 언어는 일반적으로 두 번째 클래스에서 파생 클래스가 두 개 및 첫 번째 클래스에서 파생 된 두 번째 클래스는 순환 상속을 방지 합니다. 예를 들어 한 사람이 자신의 종속 안, 비즈니스 논리를 표현 하 제약 조건을 사용할 수 있습니다. [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]도메인 특정 언어에 가장 필요로 하는 제한의 종류를 표현 하 제약 조건을 사용 합니다.  
  
### <a name="artifact-generation"></a>아티팩트 생성  
 도메인 특정 언어의 주 목적 중 하나는 아티팩트 소스 코드 예를 들어, XML 파일로 또는 일부 기타 유용한 데이터를 생성 하는 것입니다. 일반적으로 모델에 변경 아티팩트의 변경을 의미합니다. 사용할 수 있습니다 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] 아티팩트를 생성 하 고 모델을 변경한 경우 파일을 다시 생성 합니다.  
  
### <a name="serialization"></a>Serialization  
 도메인 특정 언어 수 편집, 저장, 종료 하 고 다시 로드 하는 어떤 형태로 유지 해야 합니다. [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]정의 하 고 도메인 특정 언어 serialize 되거나 유지 방법을 사용자 지정할 수 있는 XML 형식을 사용 합니다.  
  
### <a name="integration-with-visual-studio"></a>Visual Studio와의 통합  
 때문에 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] 에서 호스팅되는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 많은 확장 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 창과 컨트롤입니다. 또한 메뉴 명령, 도구 상자 항목 및 기타 요소는 사용자 인터페이스의 동작을 사용자 지정할 수 있습니다.  
  
 도메인 특정 언어에 대 한 모델 버스 어댑터를 만들 수도 있습니다. 이 어댑터 모델 참조 및 모델과 액세스 하는 DSL의 인스턴스를 업데이트할 수 있는 코드를 작성할 수 있습니다 내 요소 수 있습니다. 강력한 모델 버스 메커니즘을 사용 하 여 쓸 수 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 여러 모델을 사용 하는 확장 합니다. 또한 모델을 사용 하는 독립 실행형 응용 프로그램을 작성할 수 있습니다. 자세한 내용은 참조 [Visual Studio Modelbus를 사용 하 여 모델 통합](../modeling/integrating-models-by-using-visual-studio-modelbus.md)합니다.  
  
## <a name="benefits-of-domain-specific-development"></a>도메인 특정 개발의 이점  
 도메인 특정 언어는 다음과 같은 이점을 제공할 수 있습니다.  
  
-   문제 공간을 정확 하 게 맞는 구문을 포함 합니다.  
  
     범용 언어와 달리 도메인 특정 언어 요소와 구성 되어 직접 꼽자면 문제의 논리를 나타내는 관계입니다. 예를 들어, 보험 정책 응용 프로그램 정책 및 클레임에 대 한 요소를 포함 해야 합니다. 도메인 특정 언어 쉽게 응용 프로그램 및 찾기 및 논리의 오류를 수정 디자인할 수 있습니다.  
  
-   개발자나 사용자에 게 이해 하 고 전반적인 디자인 도메인 알지 못할 수 있습니다.  
  
     그래픽 도메인 특정 언어를 사용 하면 개발자가 응용 프로그램의 디자인을 쉽게 이해할 수 있도록 시각적으로 도메인을 만들 수 있습니다.  
  
-   최종 응용 프로그램과의 프로토타입을 만드는 쉽게 있습니다.  
  
     개발자는 클라이언트에 표시할 수 있는 프로토타입 응용 프로그램을 만들려면 해당 모델을 생성 하는 코드를 사용할 수 있습니다.  
  
## <a name="the-process-of-domain-specific-development"></a>도메인 특정 개발 프로세스  
 도메인 특정 언어를 사용 하는 대부분 소프트웨어 개발 팀을 만들고 해당 모델을 사용 하 여 다음이 단계를 따릅니다.  
  
-   팀에서 변경 되지 않는 도메인의 변수 부분을 구분 합니다.  
  
-   개발자는 고정된 부분에 대 한 코드를 작성 하 고 변수 부분에 대 한 확장 지점을 둡니다.  
  
-   수석 소프트웨어 개발자 또는 설계자 도메인과 변수 부분에 대 한 확장 지점 고정 부분의 디자인 패턴을 통합 하는 도메인 특정 언어를 만듭니다.  
  
-   설계자 또는 수석 소프트웨어 개발자 팀에서 생성 하는 다양 한 응용 프로그램 개발자에 게 도메인 특정 언어를 배포 합니다.  
  
-   모든 개발자는 특정 응용 프로그램에 적용 되는 모델을 만듭니다.