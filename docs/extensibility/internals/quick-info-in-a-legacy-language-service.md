---
title: "레거시 언어 서비스에 대 한 요약 정보 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "언어 서비스 [관리 되는 패키지 프레임 워크]에서 지 원하는 요약 정보"
  - "IntelliSense, 요약 정보"
  - "IntelliSense 요약 정보 언어 서비스 [관리 되는 패키지 프레임 워크]"
ms.assetid: 159ccb0b-f5d6-4912-b88b-e9612924ed5e
caps.latest.revision: 16
caps.handback.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 언어 서비스에 대 한 요약 정보
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

사용자 중 하나는 식별자에 캐럿 배치를 선택 하는 경우 IntelliSense 요약 정보 소스에서 식별자에 대 한 정보를 표시 **요약 정보** 에서 **IntelliSense** 메뉴 또는 식별자 위로 마우스 커서를 보유 합니다. 이렇게 하면 도구 설명의 식별자에 대 한 정보가 표시 됩니다. 이 정보는 식별자 형식을 일반적으로 구성 됩니다. 디버그 엔진 활성화 되 면 현재 값이이 정보에 포함 될 수 있습니다. 언어 서비스 식별자만 처리 하는 동안 디버그 엔진은 식 값을 제공 합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 되는 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 새로운 방법입니다. 자세한 내용을 참조 하십시오 [연습: 요약 정보 도구 설명 표시](../../extensibility/walkthrough-displaying-quickinfo-tooltips.md)합니다.  
  
> [!NOTE]
>  새 편집기 API를 최대한 빨리 사용을 시작 하는 것이 좋습니다. 이 언어 서비스의 성능을 향상 하 고 새로운 편집기 기능을 이용할 수 있도록 합니다.  
  
 IntelliSense 요약 정보 도구 설명 표시 하기 위한 모든 지원을 제공 하는 관리 되는 패키지 프레임 워크 \(MPF\) 언어 서비스 클래스. 표시 되 고 요약 정보 기능을 사용 하는 텍스트를 입력 하면 됩니다.  
  
 호출 하 여 표시 될 텍스트를 가져옵니다는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드 파서 구문 분석 이유 값 <xref:Microsoft.VisualStudio.Package.ParseReason>합니다. 이러한 이유 때문에 형식 정보 \(또는 적절 한 요약 정보 도구 설명에 표시할 무엇이\)를 가져오려면 파서에 지시에 지정 된 위치에 식별자는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 개체입니다.<xref:Microsoft.VisualStudio.Package.ParseRequest> 개체에 전달 되는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드.  
  
 파서는에서 위치까지 모든 항목을 구문 분석 해야는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 종류의 모든 식별자를 결정 하기 위해 개체입니다. 그런 다음 파서가 구문 분석 요청 위치에 식별자를 가져와야 합니다. 마지막으로, 파서를 해당 식별자와 연결 된 도구 설명 데이터를 전달 해야는 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 해당 개체에서 텍스트를 반환할 수 있도록 개체는 <xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDataTipText%2A> 메서드.  
  
## 요약 정보 기능을 사용 하면  
 요약 정보 기능을 사용 하려면 설정 해야는 `CodeSense` 및 `QuickInfo` 명명 된의 매개 변수는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute>합니다. 이러한 특성이 설정 된 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCodeSense%2A> 및 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableQuickInfo%2A> 속성입니다.  
  
## 요약 정보 기능을 구현합니다.  
 <xref:Microsoft.VisualStudio.Package.ViewFilter> IntelliSense 요약 정보 작업을 처리 하는 클래스입니다. 때는 <xref:Microsoft.VisualStudio.Package.ViewFilter> 받은 클래스는 <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> 명령, 클래스를 호출 하 여는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 의 구문 분석 이유인 메서드 <xref:Microsoft.VisualStudio.Package.ParseReason> 및 시간에 나타나는 캐럿의 위치는 <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> 명령을 보냈습니다.<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드 파서 다음 지정된 된 위치까지 소스 구문 분석 하 고 다음 요약 정보 도구 설명에 표시할 작업을 결정 하는 지정 된 위치에 대 한 식별자를 구문 분석 합니다.  
  
 대부분 파서 전체 소스 파일의 초기는 구문 분석을 수행 하 고 구문 분석 트리에 결과 저장 합니다. 전체 구문 분석이 수행 될 때 <xref:Microsoft.VisualStudio.Package.ParseReason> 에 전달 되는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드. 다른 종류의 구문 분석, 구문 분석 트리 사용 하 여 원하는 정보를 얻을 수 있습니다.  
  
 예를 들어의 구문 분석 이유 값 <xref:Microsoft.VisualStudio.Package.ParseReason> 원본 위치에서 식별자를 찾아 형식 정보를 가져오는 구문 분석 트리에서 찾아볼 수 있습니다. 이 형식 정보 전달 되어는 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 클래스를에서 반환 되는 <xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDataTipText%2A> 메서드.