---
title: "DSL 라이브러리를 사용하여 DSL 간에 클래스 공유 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 509bd96b-3e66-47f4-8642-771421d0d0d5
caps.latest.revision: 7
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 7
---
# DSL 라이브러리를 사용하여 DSL 간에 클래스 공유
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

에 있는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 시각화 및 모델링 SDK를 만들 수 있습니다 다른 DSL로 가져올 수 있습니다 불완전 한 DSL 정의 합니다.  비슷한 모델의 일반적인 부분을 구분할 수 있습니다.  
  
## 만들기 및 DSL 라이브러리 사용  
  
#### DSL 라이브러리를 만들려면  
  
1.  DSL 새 프로젝트를 만들고 라이브러리 DSL 솔루션 템플릿을 선택 합니다.  
  
     빈 모델을 단일 DSL 프로젝트가 만들어집니다.  
  
2.  도메인 클래스, 관계, 셰이프를 추가할 수 있습니다.  
  
     포함 단일 트리를 만들려면 요소 라이브러리에 없습니다.  
  
     가져오기 도구를 사용 하는 관계를 정의 하려면 두 도메인 클래스를 만들고 이들 사이의 관계를 만듭니다.  
  
     설정을 고려의  **상속 한정자** 의 도메인 클래스에 `Abstract`.  
  
3.  연결 작성기와 같은 DSL 탐색기에서 정의 하는 요소를 추가할 수 있습니다.  
  
4.  제약 조건 유효성 검사와 같은 추가 코드에 필요한 사용자 지정을 추가할 수 있습니다.  
  
5.  클릭  **서식 파일을 모두 변환**.  
  
6.  프로젝트를 빌드합니다.  
  
7.  DSL을 사용 하 여 다른 사람에 대 한 배포 하는 경우 컴파일된 어셈블리 \(DLL\)와 파일을 모두 제공 해야 `DslDefinition.dsl`.  아래의 폴더에 컴파일된 어셈블리를 찾을 수 있습니다.`Dsl\bin\*`  
  
#### DSL 라이브러리를 가져오려면  
  
1.  다른 DSL 정의  **DSL 탐색기**는 DSL의 루트 클래스를 마우스 오른쪽 단추로 클릭 하 고 다음을 클릭  **새 DslLibrary 가져오기 추가**.  
  
2.  속성 창에서 설정에서  **파일 경로** 라이브러리의.  상대 또는 절대 경로 사용할 수 있습니다.  
  
     가져온된 라이브러리 DSL 탐색기에서 읽기 전용 모드로 표시 됩니다.  
  
3.  가져온된 클래스를 기본 클래스로 사용할 수 있습니다.  가져오는 DSL에 도메인 클래스를 만들고 속성 창에서 설정  **기본 클래스** 가져온 클래스입니다.  
  
4.  클릭 모든 서식 파일을 변환 합니다.  
  
5.  DSL 프로젝트에 DSL 라이브러리 프로젝트에서 빌드된 어셈블리 \(DLL\)에 대 한 참조를 추가 합니다.  
  
6.  솔루션을 빌드합니다.  
  
 DSL 라이브러리는 다른 라이브러리를 가져올 수 있습니다.  해당 가져오기 라이브러리를 가져올 때 자동으로 DSL 탐색기에 나타납니다.  
  
## 참고 항목  
 [도메인별 언어 정의 방법](../modeling/how-to-define-a-domain-specific-language.md)