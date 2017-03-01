---
title: "도메인별 언어 솔루션 템플릿 선택 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language Tools, solution templates
ms.assetid: 9c05955f-1548-4df6-b09b-4b348823c237
caps.latest.revision: 24
author: alancameronwills
ms.author: awills
manager: douge
translationtype: Machine Translation
ms.sourcegitcommit: fd26c504273cae739ccbeef5e406891def732985
ms.openlocfilehash: 2a1ad374c709b9575ff8e3d46bb3d2178a1c3f95
ms.lasthandoff: 02/22/2017

---
# <a name="choosing-a-domain-specific-language-solution-template"></a>도메인별 언어 솔루션 템플릿 선택
도메인별 언어 솔루션을 만들려면 도메인별 언어 디자이너 마법사에서 사용할 수 있는 솔루션 템플릿 중 하나를 선택 합니다. 가장 유사한 만들려는 언어 서식 파일을 선택 하면 시작 솔루션을 변경 해야 하는 수정 작업을 최소화할 수 있습니다.  
  
 다음 솔루션 템플릿은 도메인별 언어 디자이너 마법사에서 사용할 수 있습니다.  
  
|템플릿|기능|설명|  
|--------------|--------------|-----------------|  
|클래스 다이어그램|-구획 모양<br />클래스 상속<br />관계 상속<br />-모양 상속<br />-관계 속성|도메인별 언어 엔터티 및 속성이 있는 관계를 포함 하는 경우이 솔루션 템플릿을 사용 합니다. 이 템플릿은 UML 클래스 다이어그램을 유사한 도메인별 언어를 만듭니다. 기본 엔터티는 클래스 및 인터페이스, 연결, 일반화, 및 구현 관계와 함께 합니다. 클래스 또는 인터페이스의 특성 목록을 포함 하는 상자로 나타납니다.|  
|구성 요소 다이어그램|-포트|도메인별 언어 구성 요소, 즉, 소프트웨어 시스템의 부분에 포함 된 경우이 솔루션 템플릿을 사용 합니다. 이 템플릿은 UML 구성 요소 다이어그램을 유사한 도메인별 언어를 만듭니다. 기본 엔터티는 구성 요소 및 구성 요소 외부에 있는 작은 모양으로 표시 되는 포트입니다.|  
|작업 흐름 다이어그램|-이미지 및 기 하 도형<br />-   *스윔 레인*|도메인별 언어 워크플로, 상태, 또는 시퀀스를 포함 하는 경우이 솔루션 템플릿을 사용 합니다. 이 템플릿은 UML 동작 다이어그램을 유사한 도메인별 언어를 만듭니다. 주 엔터티는는 활동 및 기본 관계는 활동 간 전환 합니다. 서식 파일에 동기화 표시줄, 시작 상태 및 최종 상태 등 여러 다른 요소에 포함 됩니다.|  
|최소 언어|-하나의 클래스 및 모양<br />-하나의 관계 및 연결선|도메인별 언어의 다른 템플릿을 비슷하지 않을 경우이 솔루션 템플릿을 사용 합니다. 이 템플릿은 두 개의 클래스와에 표시 되는 하나의 관계만 있는 도메인별 언어 만듭니다는 **도구 상자** 으로 **상자** 및 **줄**합니다. 클래스 및 관계는 각는 예제에서는 문자열 속성이 있습니다.|  
|최소 WinForm Designer|-A 작은 모델입니다.<br />-Windows Form 모델을 표시 합니다.|DSL 그래픽 디자이너 보다는 Windows Form에 바인딩된 응용 프로그램을 작성 하려는 경우이 서식 파일을 사용 합니다.<br /><br /> 사용자 인터페이스 언어에 대 한 역할을 하는 양식이 Dsl\UI 폴더에서입니다.<br /><br /> 폼 디자이너를 열기 전에 프로젝트가 빌드되어야 합니다.<br /><br /> 자세한 내용은 참조 [Windows Forms-Based 도메인별 언어 만들기](../modeling/creating-a-windows-forms-based-domain-specific-language.md)합니다.|  
|최소 WPF Designer|-작은 모델<br />-모델을 표시 하는 Windows Presentation Foundation 사용자 인터페이스 A|DSL 그래픽 디자이너 보다는 WPF 사용자 인터페이스에 바인딩된 응용 프로그램을 작성 하려는 경우이 서식 파일을 사용 합니다.<br /><br /> 사용자 인터페이스에 대 한 디자이너는 Dsl\UI 폴더에 있습니다.<br /><br /> UI 디자이너를 열기 전에 프로젝트가 빌드되어야 합니다.<br /><br /> 자세한 내용은 참조 [WPF-Based 도메인별 언어 만들기](../modeling/creating-a-wpf-based-domain-specific-language.md)합니다.|  
|DSL 라이브러리|-최소 라이브러리|다른 DSL 정의로 가져올 수 있는 부분 DSL 정의 빌드 하려는 경우이 서식 파일을 사용 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [도메인별 언어 도구 개요](../modeling/overview-of-domain-specific-language-tools.md)

