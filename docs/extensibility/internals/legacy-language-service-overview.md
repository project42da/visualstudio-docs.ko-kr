---
title: "레거시 언어 서비스 개요 | Microsoft Docs"
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
  - "언어 서비스에 대 한 언어 서비스 [관리 되는 패키지 프레임 워크]"
ms.assetid: bb44e27b-d228-463c-b2cf-cd5c24c7c1b5
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 언어 서비스 개요
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

특정 구현할 수 있도록 편집기 지원 언어 서비스 제공 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 기능.  자주 사용 하는 기능 및 기타 기능에 대 한 부분적 지원에 대 한 완벽 한 지원 패키지 관리 프레임 워크 \(MPF\) 언어 서비스 클래스를 제공합니다.  
  
## MPF에서 완벽 하 게 지원 되는 기능  
 MPF 언어 서비스 클래스는 다음과 같은 기능을 지원합니다.  
  
-   구문 강조 표시  
  
-   개요  
  
-   코드 블록의 주석 달기  
  
-   중괄호 일치  
  
-   코드 조각  
  
-   사용자 지정 문서 속성  
  
-   IntelliSense 매개 변수 정보  
  
-   IntelliSense 빠른 정보  
  
-   IntelliSense 멤버가 완료  
  
-   IntelliSense 단어 완성  
  
## MPF에서 부분적으로 지원 되는 기능  
 MPF 부분만 지원은 다음과 같은 기능을 제공합니다.  MPF에서 호출 되는 메서드를 구현 해야 한다는 것을 의미 합니다.  
  
-   코드 서식을 다시 지정 합니다.  서식을 구현 하는 코드를 제공 합니다.  
  
-   올바른 코드를 확인 하 여 중단점 확인 하는 중에 걸쳐 있습니다.  코드 범위를 식별 하는 코드를 제공 합니다.  
  
-   디버거에서 지 원하는  **자동** 변수를 표시 하는 창입니다.  창에 표시할 내용을 결정 하는 코드를 제공 합니다.  
  
-   지는  **탐색 모음** 형식 및 멤버 간의 빠른 탐색을 위해.  구현 하 고 목록을 채우는 도우미 클래스를 반환의  **탐색 모음** 콤보 상자입니다.  
  
## 구현  
 언어 서비스 및 해당 언어를 지 원하는 언어 서비스 기능을 구현 하려면 몇 가지 단계를 완료 해야 합니다.  이러한 단계는 다음 항목에서 설명 합니다.  
  
-   [언어 서비스 구현](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
  
-   [언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)  
  
-   [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)  
  
-   [중괄호 일치 레거시 언어 서비스](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스 개요](../../extensibility/internals/outlining-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 코드를 주석 달기](../../extensibility/internals/commenting-code-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 코드를 다시 포맷](../../extensibility/internals/reformatting-code-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스에서 사용자 지정 문서 속성](../../extensibility/internals/custom-document-properties-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 코드 조각에 대 한 지원](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스에 탐색 모음에 대 한 지원](../../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스에 단어 완성](../../extensibility/internals/word-completion-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스에서 멤버 완성](../../extensibility/internals/member-completion-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 매개 변수 정보](../../extensibility/internals/parameter-info-in-a-legacy-language-service2.md)  
  
-   [레거시 언어 서비스에 대 한 요약 정보](../../extensibility/internals/quick-info-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 자동 창에 대 한 지원](../../extensibility/internals/support-for-the-autos-window-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스에 있는 중단점의 유효성 검사](../../extensibility/internals/validating-breakpoints-in-a-legacy-language-service.md)  
  
## 참고 항목  
 [레거시 언어 서비스 구현](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [레거시 언어 서비스 확장](../../extensibility/internals/legacy-language-service-extensibility.md)