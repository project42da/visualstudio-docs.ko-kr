---
title: 도메인 특정 언어 솔루션 템플릿을 선택 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language Tools, solution templates
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: bfbb5c7fc82f4f41d0c15b0462b0eb7202df78aa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="choosing-a-domain-specific-language-solution-template"></a>도메인별 언어 솔루션 템플릿 선택
도메인 특정 언어 솔루션을 만들려면 도메인 특정 언어 디자이너 마법사에서 사용할 수 있는 솔루션 템플릿 중 하나를 선택 합니다. 가장 유사한 만들려는 언어 서식 파일을 선택 하 여 시작 솔루션에 확인 해야 하는 수정 작업을 최소화할 수 있습니다.  
  
 다음 솔루션 템플릿은 도메인 특정 언어 디자이너 마법사에서 사용할 수 있습니다.  
  
|템플릿|기능|설명|  
|--------------|--------------|-----------------|  
|클래스 다이어그램|-구획 모양<br />클래스 상속<br />-관계 상속<br />셰이프 상속<br />-관계 속성|도메인 특정 언어 엔터티 및 속성을 가진 관계를 포함 하는 경우이 솔루션 템플릿을 사용 합니다. 이 템플릿은 UML 클래스 다이어그램을 유사한 도메인 특정 언어를 만듭니다. 기본 엔터티는 클래스 및 인터페이스, 연결, 일반화 및 구현이 관계와 함께 합니다. 클래스 또는 인터페이스의 특성 목록을 포함 하는 상자로 나타납니다.|  
|구성 요소 다이어그램|-포트|도메인 특정 언어 구성 요소, 즉, 소프트웨어 시스템의 일부를 포함 하는 경우이 솔루션 템플릿을 사용 합니다. 이 템플릿은 UML 구성 요소 다이어그램 유사한 도메인 특정 언어를 만듭니다. 기본 엔터티는 구성 요소 및 구성 요소 외부에 있는 작은 모양으로 표시 되는 포트입니다.|  
|작업 흐름 다이어그램|-이미지 및 도형을 기 하 도형<br />-   *스윔 레인*|도메인 특정 언어 워크플로, 상태 또는 시퀀스를 포함 하는 경우이 솔루션 템플릿을 사용 합니다. 이 템플릿은 UML 동작 다이어그램 유사한 도메인 특정 언어를 만듭니다. 주 엔터티는는 활동 및 기본 관계는 활동 간 전환 합니다. 서식 파일에 시작 상태, 최종 상태는 동기화 막대 등 여러 다른 요소에 포함 됩니다.|  
|최소 언어|-하나의 클래스 및 모양<br />-하나의 관계 및 커넥터|도메인 특정 언어에서는 다른 템플릿에 비슷하지 않을 경우이 솔루션 템플릿은 사용 합니다. 이 템플릿은 두 개의 클래스 및에 표시 되는 하나의 관계를 포함 하는 도메인 특정 언어 만듭니다는 **도구 상자** 으로 **상자** 및 **줄**합니다. 클래스 및 관계는 각 예에서는 문자열 속성이 있어야 합니다.|  
|최소 WinForm 디자이너|-는 작은 모델입니다.<br />-Windows Form 모델을 표시 합니다.|DSL은 그래픽 디자이너를 사용 하지 않고 Windows Form에 바인딩하는 응용 프로그램을 빌드 하려는 경우이 템플릿을 사용 합니다.<br /><br /> 사용자 인터페이스 언어에 대 한 역할을 하는 폼은 Dsl\UI 폴더에 있습니다.<br /><br /> 프로젝트의 폼 디자이너를 열기 전에 빌드되어야 합니다.<br /><br /> 자세한 내용은 참조 [Windows Forms-Based 도메인 특정 언어를 만드는](../modeling/creating-a-windows-forms-based-domain-specific-language.md)합니다.|  
|최소한의 WPF 디자이너|-작은 모델<br />-모델을 표시 하는 A Windows Presentation Foundation 사용자 인터페이스|DSL은 그래픽 디자이너를 사용 하지 않고 WPF 사용자 인터페이스에 바인딩하는 응용 프로그램을 빌드 하려는 경우이 템플릿을 사용 합니다.<br /><br /> 디자이너 사용자 인터페이스에 대 한이 Dsl\UI 폴더에 있습니다.<br /><br /> UI 디자이너 열기 전에 프로젝트가 빌드되어야 합니다.<br /><br /> 자세한 내용은 참조 [WPF-Based 도메인 특정 언어를 만드는](../modeling/creating-a-wpf-based-domain-specific-language.md)합니다.|  
|DSL 라이브러리|-최소 라이브러리|이 서식 파일을 사용 하 여 다른 DSL 정의로 가져올 수 있는 부분 DSL 정의 빌드 하려는 경우.|  
  
## <a name="see-also"></a>참고 항목  
 [도메인별 언어 도구 개요](../modeling/overview-of-domain-specific-language-tools.md)
