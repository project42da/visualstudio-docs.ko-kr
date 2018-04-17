---
title: 레거시 언어 서비스 Essentials | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- languages, integrating into Visual Studio
- language services, integrating programming languages
- Visual Studio, integrating programming languages
- programming languages, integrating into Visual Studio
ms.assetid: c15e0ccb-e7c5-4dbb-affb-fe3d3244debe
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 68b92b821ad77b050ad2116da6fd930b975dad5a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="legacy-language-service-essentials"></a>레거시 언어 서비스 Essentials
Visual Studio에는 프로그래밍 언어를 통합 하는 언어 서비스를 제공 해야 합니다. 이 항목에서는 레거시 언어 서비스에서 사용할 수 있는 기능을 설명 합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 된 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 최신 방법입니다. 언어 서비스를 구현 하는 새로운 방법에 대해 자세히 알아보려면 참조 [편집기와 언어 서비스 확장](../../extensibility/editor-and-language-service-extensions.md)합니다.  
  
> [!NOTE]
>  편집기를 사용 하 여 새 API 가능한 한 빨리 시작 하는 것이 좋습니다. 언어 서비스의 성능이 향상 되 고 새 편집기 기능을 이용할 수 있도록 합니다.  
  
 레거시 언어 서비스는 다음과 같은 기능을 제공합니다.  
  
|기능|설명|  
|-------------|-----------------|  
|구문 색 지정|서로 다른 색 및 언어의 다양 한 요소에 대 한 글꼴 스타일을 표시 하려면 편집기 보기를 하면 됩니다. 이러한 구분을 읽고 편집할 파일을 쉽게 만들 수 있습니다.<br /><br /> 일반 정보를 참조 하십시오. [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)합니다.<br /><br /> MPF ()는 관리 패키지 프레임 워크에서이 기능에 대 한 정보를 참조 하십시오. [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)합니다.|  
|문 완성|문 또는 키워드를 입력 하는 사용자가 시작을 완료 합니다. 문 완성 사용자가 입력 및 오류에 대 한 더 적은 가능성 어려운 문을 더 쉽게 입력할 수 있습니다.<br /><br /> 일반 정보를 참조 하십시오. [레거시 언어 서비스에서 문 완성](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md)합니다.<br /><br /> MPF에서이 기능에 대 한 정보를 참조 하십시오. [레거시 언어 서비스에서 단어 완성](../../extensibility/internals/word-completion-in-a-legacy-language-service.md)합니다.|  
|중괄호 일치|중괄호 등의 문자 쌍이 강조 표시 합니다. 때 사용자 등의 형식은 닫는 문자 "을 (를)", 중괄호 일치와 같은 여는 문자가, 해당 강조 표시 "{"입니다. 문자를 포함 하는 여러 수준의 경우이 기능은 사용자가 바깥쪽 문자 쌍이 올바른지 확인 합니다.<br /><br /> MPF에서이 기능에 대 한 정보를 참조 하십시오. [레거시 언어 서비스에서 중괄호 일치](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)합니다.|  
|매개 변수 정보 도구 설명|현재 사용자가 입력 하는 오버 로드 된 메서드에 대 한 가능한 서명 목록에 표시 됩니다.<br /><br /> 일반 정보를 참조 하십시오. [레거시 언어 서비스에 대 한 매개 변수 정보](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md)합니다.<br /><br /> MPF에서이 기능에 대 한 정보를 참조 하십시오. [레거시 언어 서비스에 대 한 매개 변수 정보](../../extensibility/internals/parameter-info-in-a-legacy-language-service2.md)합니다.|  
|오류 표식|빨강 물결선 밑줄, 라고도 구불구불한, 구문이 잘못 된 텍스트 아래에 표시 됩니다. 사용자가의 철자가 잘못 된 키워드, 닫히지 않은 괄호가, 잘못 된 문자 및 유사한 오류가 인식 하 게 하는 일반적으로 오류 표식이 사용 됩니다.<br /><br /> MPF 클래스 오류 표식에는 자동으로 처리 됩니다는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.AddError%2A> 의 메서드는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 클래스입니다.|  
  
 이러한 기능 중 대부분은 언어 서비스 소스 코드를 구문 분석할 필요 합니다. 자주 다시 사용할 수 있습니다는 토큰화 및 컴파일러 또는 인터프리터에 대 한 코드를 구문 분석 합니다.  
  
 다음과 같은 기능이 프로그래밍 언어에 대 한 지원 관련 되어 있지만 언어 서비스의 일부가 아닙니다.  
  
|기능|설명|  
|-------------|-----------------|  
|식 계산기|지원 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 에 표시할 중단점 유효성을 검사 하 고 식의 목록을 제공 디버거는 **자동** 디버그 창.<br /><br /> 자세한 내용은 참조 [디버깅에 대 한 언어 서비스 지원](../../extensibility/internals/language-service-support-for-debugging.md)합니다.|  
|기호 검색 도구|지원 **개체 브라우저**, **클래스 뷰**, **호출 브라우저**, 및 **기호 찾기 결과**합니다.|