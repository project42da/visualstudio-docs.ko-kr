---
title: "레거시 언어 서비스 확장 | Microsoft Docs"
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
  - "언어 서비스"
  - "Visual Studio 언어 서비스"
ms.assetid: 2700cd4d-5f68-43fc-b62f-dc80c3f3aa85
caps.latest.revision: 42
caps.handback.revision: 42
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 언어 서비스 확장
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

언어 서비스는 IDE에서 소스 코드 편집 언어 관련 지원을 제공 합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 되는 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 새로운 방법입니다. 언어 서비스를 구현 하는 새로운 방법에 대 한 자세한 내용을 참조 하십시오 [편집기와 언어 서비스 확장](../../extensibility/editor-and-language-service-extensions.md)합니다.  
  
 이 섹션에서는 구조와 레거시 언어 서비스의 구현을 설명 합니다.  
  
## 단원 내용  
 [레거시 언어 서비스 마이그레이션](../../extensibility/internals/migrating-a-legacy-language-service.md)  
 최신 버전으로 Visual Studio 2008에서 언어 서비스를 업데이트 하는 방법에 설명 합니다.  
  
 [레거시 언어 서비스 Essentials](../../extensibility/internals/legacy-language-service-essentials.md)  
 Visual Studio에는 프로그래밍 언어를 통합 하기 위해 언어 서비스를 개발 하는 방법에 대 한 중요 한 정보를 제공 합니다.  
  
 [언어 서비스 개발](../../extensibility/internals/developing-a-legacy-language-service.md)  
 언어 서비스를 만들 수 있는 항목에 대 한 링크를 제공 합니다.  
  
 [구문 레거시 언어 서비스에 색 지정](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 언어 서비스에서 구문 강조 지원에 대 한 정보를 제공 합니다.  
  
 [레거시 언어 서비스 구현](../../extensibility/internals/implementing-a-legacy-language-service1.md)  
 관리 코드의 모든 기능을 갖춘 언어 서비스를 구현 하는 관리 되는 패키지 프레임 워크 \(MPF\)를 사용 하는 방법에 대 한 정보를 제공 합니다.  
  
 [기호 검색 도구를 지원합니다.](../../extensibility/internals/supporting-symbol-browsing-tools.md)  
 라이브러리 및 IDE에서 기호의 트리 뷰를 찾아볼 수 있도록 하는 도구에 설명 합니다.  
  
## 관련 단원  
 [편집기와 언어 서비스 확장](../../extensibility/editor-and-language-service-extensions.md)  
 Visual Studio 편집기에 간략하게 설명 합니다.  
  
 [디버깅 하기 위한 언어 서비스 지원](../../extensibility/internals/language-service-support-for-debugging.md)  
 Visual Studio 디버깅 sdk 만들고 프로그램을 디버깅 하는 데 사용 되는 디버거 구성 요소를 사용자 지정 하는 데 필요한 정보가 포함 되어에 대 한 정보 및 링크를 제공 합니다.