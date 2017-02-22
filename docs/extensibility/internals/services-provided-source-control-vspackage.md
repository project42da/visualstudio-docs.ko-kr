---
title: "제공 하는 서비스 (소스 제어 VSPackage) | Microsoft Docs"
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
  - "서비스, 소스 제어 패키지"
  - "소스 제어 패키지 서비스"
ms.assetid: 9db07d70-87d2-4401-bc88-e3a49d81e9a2
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# 제공 하는 서비스 (소스 제어 VSPackage)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

서비스를 기능 및 Visual Studio 통합된 개발 환경 \(IDE\)와 해당 설치 된 VSPackages VSPackages 사이에서 공유 하는 기본 메커니즘입니다.  자세한 서비스와 Visual Studio IDE의 중요성에 대 한 참조[사용 하 고 서비스를 제공 합니다.](../../extensibility/using-and-providing-services.md).  
  
## 소스 제어 서비스  
 Visual Studio 두 레이어 서비스, IDE 수준의 서비스와 패키지 수준 서비스를 제공합니다.  Visual Studio IDE는 기본적으로 IDE 수준의 서비스를 제공합니다.  소스 제어 패키지는 이러한 서비스 중 일부를 사용합니다.  소스 제어 패키지는 Vspackage로 별도의 전용 소스 제어 서비스를 제공 하 여 소스 제어 기능을 공유 합니다.  소스 제어 패키지는 소스 제어와 관련 된 인터페이스 Visual Studio IDE에서 사용할 수 있는 계약의 형태로 구현 집합을 캡슐화 합니다.  
  
## 참고 항목  
 [디자인 요소](../../extensibility/internals/source-control-vspackage-design-elements.md)