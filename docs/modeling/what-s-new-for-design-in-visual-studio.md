---
title: "Visual Studio의 디자인에에서 대 한 새로운 기능 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- what's new [VIsual Studio ALM], architecture and modeling
- architecture [Visual Studio Ultimate], modeling
- modeling software [Visual Studio ALM], What's New
ms.assetid: 36ab5c17-6dc0-4075-a28e-a0fa49b11260
caps.latest.revision: 32
author: alexhomer1
ms.author: ahomer
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
translationtype: Machine Translation
ms.sourcegitcommit: 17bc5792d4fa9fac0b97705e61372dcc884c82a2
ms.openlocfilehash: 2704914ab8607e0a7442a45589e6a6cab08b7338
ms.lasthandoff: 02/22/2017

---
# <a name="what39s-new-for-design-in-visual-studio"></a>Visual Studio의 디자인에에서 대 한 새로운 기능

## <a name="live-dependency-validation"></a>라이브 종속성 유효성 검사

원치 않는 종속성을 제거 하면 기술적 문제 관리의 중요 한 부분이입니다.
종속성의 라이브 유효성 검사를 포함 하는 이제 문제에 대 한 정확한 정보를 제공 하 이며 오류 목록 및 편집기의 새로운 기능에서 완벽 하 게 혜택이 있습니다.

![라이브 종속성 유효성 검사 적용](~/modeling/media/dep-validation-whatsnew-01.png)

제작 환경을 하려면 종속성 유효성 검사를 더 쉽게 검색할 수 및 보다 쉽게 액세스할 수 변경 "종속성 다이어그램"를 "레이어 다이어그램" 용어 변경 되었습니다.

**아키텍처** 메뉴에는 이제 직접 종속성 다이어그램을 만들려면 명령이 포함 되어 있습니다.

![라이브 종속성 메뉴에서 항목의 아키텍처](~/modeling/media/dep-validation-whatsnew-02.png)

... 및 종속성 다이어그램 및 해당 설명에는 계층의 속성 이름을 알기 쉬운 하도록 변경 되었습니다.

![업데이트 된 라이브 종속성 속성 이름](~/modeling/media/dep-validation-whatsnew-03.png)

이제 표시의 변경 내용을 즉시 솔루션에는 현재 코드에 대 한 분석 결과에 영향을 때마다 다이어그램을 저장 합니다. "종속성의 유효성을 검사" 명령의 완료를 더 이상 기다릴 필요가 없습니다.

자세한 내용은 다음을 참조 하십시오. [이 블로그 게시물](https://blogs.msdn.microsoft.com/visualstudioalm/2016/10/07/live-architecture-dependency-validation-in-visual-studio-15-preview-5/)합니다. 
 
## <a name="uml-designers-have-been-removed"></a>UML 디자이너 제거 되었습니다.

UML 디자이너가이 버전의 Visual Studio Enterprise에서 제거 되었습니다.

* UML 다이어그램은 이제 XML 파일로 표시
* UML 모델 탐색기 더 이상 존재합니다.
* 모델링 프로젝트 참조는 종속성 유효성 검사를 위해 더 이상 사용 됩니다.
* 솔루션 탐색기에서 "레이어 참조" 노드는 더 이상 표시 되지
* "유효성 검사" 빌드 작업 (계층) 종속성 다이어그램에 더 이상 사용-빌드 작업에서 제거 되었습니다. 
* 버전 간 왕복에 대 한 유지 관리 됩니다 프로젝트 구조
* 있습니다 여전히 열기, 만들기, 편집 하 고 수 (계층) 종속성 다이어그램을 XML로 저장 합니다.
* 디자인 화면에 액세스할 수 없는 (계층) 종속성 다이어그램에 연결 된 TFS 작업 항목
* 다시 연결에서 DSL 또는 계층은 더 이상 지원 
* UML 확장성 모델링 SDK에는 더 이상 지원 되지

그러나.NET 및 c + + 코드의 아키텍처를 시각화를 통해 이용하실 수에 대 한 지원 [코드 맵](map-dependencies-across-your-solutions.md), 및 위에서 설명한 종속성 유효성 검사는 크게 개선 되었습니다.

UML 디자이너의 중요 한 사용자 인 경우에 UML 요구 사항에 대 한 대체 하는 도구를 결정 하는 동안 Visual Studio 2015 또는 이전 버전을 사용 하 여 계속 수 있습니다.

자세한 내용은 다음을 참조 하십시오. [이 블로그 게시물](https://blogs.msdn.microsoft.com/visualstudioalm/2016/10/14/uml-designers-have-been-removed-layer-designer-now-supports-live-architectural-analysis/)합니다. 

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

<a name="VersionSupport"></a>
##  <a name="version-support-for-architecture-and-modeling-tools"></a>아키텍처 및 모델링 도구에 대한 버전 지원  

Visual Studio는 여러 버전에서 사용할 수 있습니다. 모든 버전에서 아키텍처 및 모델링 도구가 지원되는 것은 아닙니다. 다음 표에서는 각 도구의 사용 가능 여부를 보여 줍니다.  
  
|**기능**|**엔터프라이즈**|**Professional**|**커뮤니티**|**Express**|  
|-----------------|--------------------|----------------------|-------------------|-----------------|  
|**코드 맵**|예|참고 (1)를 참조 하십시오.|-|-|  
|**종속성 다이어그램**|예|참고 (2)를 참조 하십시오.|참고 (2)를 참조 하십시오.|-|  
|**전송 그래프** (DGML 다이어그램)|예|예|예|-|  
|**코드 클론**|예|-|-|-|  
  
참고 (1): 코드 맵 읽기, 코드 맵 필터링, 새 제네릭 노드 추가, 선택 영역에서 새 전송 그래프 만들기만 지원합니다.

종속성 다이어그램 읽기 말씀 드리자면, (2)만 지원 합니다.

