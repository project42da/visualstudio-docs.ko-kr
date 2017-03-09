---
title: "Visual Studio 라이브러리 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Visual Studio 라이브러리, 개요"
ms.assetid: 48910975-7202-462f-a656-de67a4f8b14d
caps.latest.revision: 9
caps.handback.revision: 9
manager: "douge"
---
# Visual Studio 라이브러리 개요
Visual Studio 라이브러리는 네이티브 c \+ \+에서는 VSPackages 만드는 단순화에 대 한 템플릿 기반 c \+ \+ 클래스 집합입니다.  Visual Studio 라이브러리 전체 소스 코드를 c \+ \+ 헤더 파일의 집합으로 포함 되어 있습니다.  헤더 파일이 설치 되어  *Visual Studio SDK 설치 경로가*\\VisualStudioIntegration \\Common\\Source\\CPP\\VSL\\Include\\.  
  
> [!NOTE]
>  Visual Studio 라이브러리에는 ATL \(액티브 템플릿 라이브러리\) COM 개체의 지원에 의존합니다.  자세한 내용은 [ATL 소개](/visual-cpp/atl/introduction-to-atl)를 참조하십시오.  
  
 Visual Studio 라이브러리 단위 테스트 코드 자체와 코드를 모두 지원 합니다.  단위 테스트는 다음과 같은 포함 됩니다.  
  
-   Visual Studio 라이브러리 단위 테스트에 설치 된  *Visual Studio SDK 설치 경로가*\\VisualStudioIntegration\\Common\\Source\\CPP\\VSL\\UnitTest\\.  
  
-   단위 테스트의 코드에 대 한 기본 클래스에 있는  *Visual Studio SDK 설치 경로가*\\VisualStudioIntegration\\Common\\Source\\CPP\\VSL\\Include\\VSLUnitTest.h.  
  
 일반적으로 사용 되는 COM 및 Visual Studio 인터페이스의 모의 구현을 수에서 설치 되는 헤더 파일, VSLMockSystemInterfaces.h 및 VSLMockVisualStudioInterfaces.h,  *Visual Studio SDK 설치 경로가*\\VisualStudioIntegration\\Common\\Source\\CPP\\VSL\\Include\\.  
  
## 참고 항목  
 [Visual Studio Library를 사용하여 VSPackages 개발](../misc/developing-vspackages-by-using-the-visual-studio-library.md)