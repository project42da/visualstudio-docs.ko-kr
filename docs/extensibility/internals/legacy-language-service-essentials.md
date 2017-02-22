---
title: "레거시 언어 서비스 Essentials | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "언어, Visual Studio에 통합"
  - "프로그래밍 언어를 통합 하는 언어 서비스"
  - "Visual Studio에서 프로그래밍 언어를 통합 합니다."
  - "Visual Studio에 통합 하는 프로그래밍 언어"
ms.assetid: c15e0ccb-e7c5-4dbb-affb-fe3d3244debe
caps.latest.revision: 21
caps.handback.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 언어 서비스 Essentials
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Visual Studio에는 프로그래밍 언어를 통합 하는 언어 서비스를 제공 해야 합니다. 이 항목에서는 레거시 언어 서비스에서 사용할 수 있는 기능을 설명 합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 되는 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 새로운 방법입니다. 언어 서비스를 구현 하는 새로운 방법에 대 한 자세한 내용을 참조 하십시오 [편집기와 언어 서비스 확장](../../extensibility/editor-and-language-service-extensions.md)합니다.  
  
> [!NOTE]
>  새 편집기 API를 최대한 빨리 사용을 시작 하는 것이 좋습니다. 이 언어 서비스의 성능을 향상 하 고 새로운 편집기 기능을 이용할 수 있도록 합니다.  
  
 레거시 언어 서비스는 다음과 같은 기능을 제공합니다.  
  
|기능|설명|  
|--------|--------|  
|구문 색 지정|다른 색 및 언어의 다양 한 요소에 대 한 글꼴 스타일을 표시 하려면 편집기 보기를 하면 됩니다. 이러한 구분 하기가 더 보다 쉽게 읽고 파일을 편집 합니다.<br /><br /> 일반 정보를 참조 하십시오. [구문 레거시 언어 서비스에 색 지정](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)합니다.<br /><br /> 관리 되는 패키지 프레임 워크 \(MPF\)에서이 기능에 대 한 정보를 참조 하십시오. [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)합니다.|  
|문 완성|문 또는 키워드를 입력 하는 사용자가 시작을 완료 합니다. 문 완성 기능 적게 입력 및 오류에 대 한 더 적은 가능성 어려운 문을 더 쉽게 입력할 수 있습니다.<br /><br /> 일반 정보를 참조 하십시오. [레거시 언어 서비스에서 문 완성](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md)합니다.<br /><br /> MPF에서이 기능에 대 한 정보를 참조 하십시오. [레거시 언어 서비스에 단어 완성](../../extensibility/internals/word-completion-in-a-legacy-language-service.md)합니다.|  
|중괄호 일치|주요 내용 중괄호 등의 문자 쌍을 이룹니다. 사용자 형식을 때 닫는 문자와 같은 "}", 중괄호 일치 강조 표시와 같은 문자를 열어 해당 "{"입니다. 문자를 포함 하는 여러 수준의 있을 때,이 기능은 사용자는 바깥쪽 문자 쌍이 올바른지 확인 합니다.<br /><br /> MPF에서이 기능에 대 한 정보를 참조 하십시오. [중괄호 일치 레거시 언어 서비스](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)합니다.|  
|매개 변수 정보 도구 설명|현재 사용자가 입력 하는 오버 로드 된 메서드에 대 한 가능한 서명 목록을 표시 합니다.<br /><br /> 일반 정보를 참조 하십시오. [레거시 언어 서비스의 매개 변수 정보](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md)합니다.<br /><br /> MPF에서이 기능에 대 한 정보를 참조 하십시오. [레거시 언어 서비스의 매개 변수 정보](../../extensibility/internals/parameter-info-in-a-legacy-language-service2.md)합니다.|  
|오류 표식|빨강 물결선 밑줄, 라고도 구불구불한, 구문이 잘못 된 텍스트 아래에 표시 됩니다. 일반적으로 오류 표식 사용자 맞춤법 오류가 있는 키워드, 닫히지 않은 괄호, 잘못 된 문자를 및 유사한 오류가에 게 알리기 위해 사용 됩니다.<br /><br /> 오류 표식에서 자동으로 처리 MPF 클래스에는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.AddError%2A> 의 메서드는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 클래스.|  
  
 이러한 기능 중 대부분은 언어 서비스 소스 코드를 구문 분석할 필요 합니다. 자주 다시 사용할 수는 토큰화 및 컴파일러 또는 인터프리터에 대 한 코드를 구문 분석 합니다.  
  
 다음과 같은 기능 프로그래밍 언어에 대 한 지원 관련 되어 있지만 언어 서비스의 일부가 아닙니다.  
  
|기능|설명|  
|--------|--------|  
|식 계산기|지원 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 에 표시할 중단점 유효성을 검사 하 고 식의 목록을 제공 하 여 디버거는 **자동** 디버그 창입니다.<br /><br /> 자세한 내용은 [디버깅 하기 위한 언어 서비스 지원](../../extensibility/internals/language-service-support-for-debugging.md)을 참조하세요.|  
|기호 검색 도구|지원 **개체 브라우저**, **클래스 뷰**, **호출 브라우저**, 및 **기호 찾기 결과**합니다.|