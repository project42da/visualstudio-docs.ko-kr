---
title: "레거시 언어 서비스 Features1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "언어 서비스 [관리 되는 패키지 프레임 워크]"
ms.assetid: a646e4f0-767d-4cd1-8e1a-9a2aa210a1b7
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 레거시 언어 서비스 기능
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

패키지 관리 프레임 워크 \(MPF\) 언어 서비스 하나를 지원할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 구문 강조, IntelliSense, 및 중단점 유효성 검사 등과 같은 기능을 합니다.  각 기능은 서로 독립적으로 구현할 수 있습니다 하지만 모두 파서와 스캐너를 필요로 구문 강조를 제외 하 고 스캐너를 필요로 합니다.  
  
## 단원 내용  
 [중괄호 일치 레거시 언어 서비스](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)  
 언어 쌍도 일치 하는 중괄호 일치를 지 원하는 데 필요한 것에 대해 설명 합니다.  
  
 [레거시 언어 서비스의 코드를 주석 달기](../../extensibility/internals/commenting-code-in-a-legacy-language-service.md)  
 주석 달기 및 제거의 선택된 된 코드를 지원 하기 위해 필요한 것에 대해 설명 합니다.  
  
 [레거시 언어 서비스에서 사용자 지정 문서 속성](../../extensibility/internals/custom-document-properties-in-a-legacy-language-service.md)  
 소스 파일에 포함 된 문서 속성을 지원 하기 위해 필요한 것에 대해 설명 합니다.  
  
 [레거시 언어 서비스 개요](../../extensibility/internals/outlining-in-a-legacy-language-service.md)  
 숨겨진의 구현을 통해 개요를 지원 하기 위해 필요한 것에 대해 설명 합니다.  
  
 [레거시 언어 서비스의 코드를 다시 포맷](../../extensibility/internals/reformatting-code-in-a-legacy-language-service.md)  
 Reformatting 코드를 지원 하기 위해 필요한 것에 대해 설명 합니다.  
  
 [레거시 언어 서비스의 코드 조각에 대 한 지원](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md)  
 코드 조각을 삽입 하 고 편집할 수 있는 코드 세그먼트는 지원 하기 위해 필요한 것에 대해 설명 합니다.  
  
 [레거시 언어 서비스의 매개 변수 정보](../../extensibility/internals/parameter-info-in-a-legacy-language-service2.md)  
 메서드를 입력 한 대로 표시 하는 메서드 시그니처를 IntelliSense 매개 변수 정보 작업을 지원 하기 위해 필요한 것에 대해 설명 합니다.  
  
 [레거시 언어 서비스에 대 한 요약 정보](../../extensibility/internals/quick-info-in-a-legacy-language-service.md)  
 식별자에 대 한 정보를 표시 하기 위한 IntelliSense 요약 정보 작업을 지원 하기 위해 필요한 것에 대해 설명 합니다.  
  
 [레거시 언어 서비스에서 멤버 완성](../../extensibility/internals/member-completion-in-a-legacy-language-service.md)  
 목록에서 선택 하는 네임 스페이스의 멤버에 대 한 IntelliSense 구성원 완성 작업을 지원 하는 데 필요한 설명 합니다.  
  
 [레거시 언어 서비스에 단어 완성](../../extensibility/internals/word-completion-in-a-legacy-language-service.md)  
 단어 자동 완성 IntelliSense 작업을 부분적으로 입력 된 단어를 완성을 지원 하기 위해 필요한 것에 대해 설명 합니다.  
  
 [레거시 언어 서비스의 자동 창에 대 한 지원](../../extensibility/internals/support-for-the-autos-window-in-a-legacy-language-service.md)  
 언어 서비스를 지원 할 수 있는 설명의  **자동** 디버깅 하는 동안 창입니다.  
  
 [레거시 언어 서비스에 탐색 모음에 대 한 지원](../../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)  
 사용 하는 방법에 설명의  **탐색 모음** 상단에 빠른 탐색을 제공 하는 형식 또는 멤버에 해당 보기에 표시 된 파일을 편집기 보기.  
  
 [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)  
 소스 코드의 구문 강조를 지원 하기 위해 필요한 것에 대해 설명 합니다.  
  
 [레거시 언어 서비스에 있는 중단점의 유효성 검사](../../extensibility/internals/validating-breakpoints-in-a-legacy-language-service.md)  
 언어 서비스는 디버거 외부 검증 중단점을 지원 할 수 있습니다 설명 합니다.  
  
## 관련 단원  
 [레거시 언어 서비스 파서 및 검사](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)  
 파서 및 패키지 관리 되는 프레임 워크를 사용 하는 언어 서비스의 모든 기능을 구현 하는 데 필요한 스캐너를 설명 합니다.  
  
 [언어 서비스 구현](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
 MPF를 사용 하 여 언어 서비스를 구현 하는 데 필요한 무엇입니까 설명 합니다.  
  
 [언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)  
 MPF 기반 언어 서비스에 등록 하는 데 필요한 단계를 설명 합니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [IntelliSense 사용](../../ide/using-intellisense.md)  
 IntelliSense 언어 참조에 쉽게 액세스할 수 하는 방법을 설명 합니다.  
  
 [레거시 언어 서비스 구현](../../extensibility/internals/implementing-a-legacy-language-service1.md)  
 패키지 관리 프레임 워크 \(MPF\)를 사용 하 여 모든 기능을 갖춘 언어 서비스는 관리 코드에 구현 하는 방법에 대 한 정보를 제공 합니다.