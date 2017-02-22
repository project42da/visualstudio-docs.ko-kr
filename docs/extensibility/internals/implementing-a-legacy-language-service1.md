---
title: "레거시 언어 서비스 구현 | Microsoft Docs"
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
  - "관리 되는 언어 서비스"
ms.assetid: df638f24-166d-4b80-be82-c9c39ca7a556
caps.latest.revision: 18
caps.handback.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 언어 서비스 구현
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

구문 강조, 중괄호 일치 및 IntelliSense 완성 등을 지 원하는 다양 한 기능을 레거시 언어 서비스를 구현 하는 관리 되는 패키지 프레임 워크 \(MPF\)의 클래스를 사용할 수 있습니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 되는 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 새로운 방법입니다. 언어 서비스를 구현 하는 새로운 방법에 대 한 자세한 내용을 참조 하십시오 [편집기와 언어 서비스 확장](../../extensibility/editor-and-language-service-extensions.md)합니다.  
  
> [!NOTE]
>  새 편집기 API를 최대한 빨리 사용을 시작 하는 것이 좋습니다. 이 언어 서비스의 성능을 향상 하 고 새로운 편집기 기능을 이용할 수 있도록 합니다.  
  
## 단원 내용  
 [레거시 언어 서비스 개요](../../extensibility/internals/legacy-language-service-overview.md)  
 MPF에서 지원 되는 언어 서비스 기능의 개요입니다.  
  
 [언어 서비스 구현](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
 MPF를 사용 하 여 언어 서비스를 구현 하는 데 필요한 사항에 대해 설명 합니다.  
  
 [언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)  
 포함 된 언어 MPF 기반 서비스를 등록 하는 데 필요한 단계를 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 [레거시 언어 서비스 파서 및 검사](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)  
 MPF를 사용 하 여 언어 서비스의 모든 기능을 구현 하는 데 필요한 두 개의 파서를 설명 합니다.  
  
 [연습: 레거시 언어 서비스 만들기](../../extensibility/internals/walkthrough-creating-a-legacy-language-service.md)  
 VSPackage에서 MPF 언어 서비스를 구현 하는 데 필요한 기본 단계를 제공 합니다.  
  
 [연습: 설치 된 코드 조각 \(레거시 구현\)의 목록 가져오기](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md)  
 설치 된 코드 조각 목록을 검색 하는 기술을 보여 줍니다.  
  
 [레거시 언어 서비스 기능](../../extensibility/internals/legacy-language-service-features1.md)  
 실행 되어야 하는 MPF를 사용 하 여 언어 서비스의 모든 기능을 구현 하는 자세한 항목에 대 한 링크를 제공 합니다.