---
title: "레거시 언어 서비스 완료 word | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- language services [managed package framework], IntelliSense Complete Word
- IntelliSense, Complete Word
- Complete Word
ms.assetid: 0ace5ac3-f9e1-4e6d-add4-42967b1f96a6
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a4ab4bd29c753fc03787fbbadbe106d2d8862b10
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="word-completion-in-a-legacy-language-service"></a>레거시 언어 서비스에서 단어 완성
단어 완성 부분적으로 형식화 된 단어에 문자가 없는 채웁니다. 하나의 가능한 완료 하는 경우 단어 완성 문자를 입력할 때 완료 됩니다. 둘 이상의 가능성 일치 하는 부분 단어 가능한 완료의 목록이 표시 됩니다. 완료 문자는 식별자에 대 한 사용 되지 않는 모든 문자를 사용할 수 있습니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 된 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 최신 방법입니다. 자세한 내용을 알아보려면 참조 [편집기 및 언어 서비스 확장](../../extensibility/extending-the-editor-and-language-services.md)합니다.  
  
> [!NOTE]
>  편집기를 사용 하 여 새 API 가능한 한 빨리 시작 하는 것이 좋습니다. 언어 서비스의 성능이 향상 되 고 새 편집기 기능을 이용할 수 있도록 합니다.  
  
## <a name="implementation-steps"></a>구현 단계  
  
1.  사용자가 선택할 때 **단어 자동 완성** 에서 **IntelliSense** 메뉴는 <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> 명령 언어 서비스로 전송 됩니다.  
  
2.  <xref:Microsoft.VisualStudio.Package.ViewFilter> 명령 및 호출 클래스를 catch는 <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> 의 구문 분석 문제의 원인이 메서드 <xref:Microsoft.VisualStudio.Package.ParseReason>합니다.  
  
3.  <xref:Microsoft.VisualStudio.Package.Source> 클래스가 다음 호출에서 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 가능한 단어 완성 및 도구 설명에 있는 단어를 사용 하 여 목록을 표시 하는 목록을 얻으려면 메서드는 <xref:Microsoft.VisualStudio.Package.CompletionSet> 클래스입니다.  
  
     이면 하나만 일치 하는 단어는 <xref:Microsoft.VisualStudio.Package.Source> 는 단어를 완성 하는 클래스입니다.  
  
 또는 스캐너 트리거 값을 반환 하는 경우 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 식별자의 첫 번째 문자를 입력할 때는 <xref:Microsoft.VisualStudio.Package.Source> 클래스에서이 점을 검색 하 고 호출 하는 <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> 의 구문 분석 문제의 원인이 메서드 <xref:Microsoft.VisualStudio.Package.ParseReason>합니다. 이 경우 파서는 멤버 선택 문자의 존재를 검색 하 고 멤버의 목록을 제공 해야 합니다.  
  
## <a name="enabling-support-for-the-complete-word"></a>단어 자동 완성에 대 한 지원을 사용 하도록 설정  
 단어 완성 집합에 대 한 지원을 사용 하도록 설정 하려면는 `CodeSense` 명명 된에 전달 된 매개 변수는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 언어 패키지와 연결 된 사용자 특성입니다. 이 설정의 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCodeSense%2A> 속성에는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 클래스입니다.  
  
 프로그램 파서 구문 분석 이유 값에 대 한 응답에서 선언의 목록을 반환 해야 <xref:Microsoft.VisualStudio.Package.ParseReason>, 단어 완성 작동할 수에 대 한 합니다.  
  
## <a name="implementing-complete-word-in-the-parsesource-method"></a>단어 자동 완성 ParseSource 메서드 구현  
 단어 완성에 대 한는 <xref:Microsoft.VisualStudio.Package.Source> 호출 클래스는 <xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDeclarations%2A> 메서드를는 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 클래스 가능한 단어 일치 항목의 목록을 가져올 수 있습니다. 목록에서 파생 된 클래스에서 구현 해야는 <xref:Microsoft.VisualStudio.Package.Declarations> 클래스입니다. 참조는 <xref:Microsoft.VisualStudio.Package.Declarations> 구현 해야 하는 방법에 대 한 세부 정보에 대 한 클래스입니다.  
  
 목록에 한 단어를 포함 하는 경우 다음의 <xref:Microsoft.VisualStudio.Package.Source> 클래스에 부분 단어 대신 해당 단어가 자동으로 삽입 합니다. 목록 여러 단어를 포함 하는 경우는 <xref:Microsoft.VisualStudio.Package.Source> 클래스 사용자 적합 한 선택 항목을 선택할 수 있는 도구 설명 목록을 표시 합니다.  
  
 또한의 예를 살펴는 <xref:Microsoft.VisualStudio.Package.Declarations> 클래스 구현이 [레거시 언어 서비스에서 멤버 완성](../../extensibility/internals/member-completion-in-a-legacy-language-service.md)합니다.