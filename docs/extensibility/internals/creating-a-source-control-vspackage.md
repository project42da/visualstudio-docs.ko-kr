---
title: "소스 제어 VSPackage 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 패키지를 만드는 소스 제어 [Visual Studio SDK]"
  - "소스 제어 패키지"
ms.assetid: cca0a9ed-48ff-409f-8036-ed8db0f7533e
caps.latest.revision: 23
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 23
---
# 소스 제어 VSPackage 만들기
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 설명서와 통합 된 소스 제어 패키지는 아키텍처 개요에 대 한 링크가 들어 있습니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]을 구현 하는 인터페이스 및 소비 하는 서비스를 정의 하는 API 및 간단한 소스 컨트롤 패키지 구현을 보여 주는 샘플입니다.  
  
 소스 제어와 VSPackage 통합 되어 소스 제어 통합에 대 한 경로 만들 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  패키지 기본 원본 컨트롤 UI 호스트를 무시할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]프로젝트 시스템의 소스 제어 요청에 응답 하 고 상호 작용 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 와 같은 구성 요소  **솔루션 탐색기**.  [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 구축할 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 파트너와 통합할 수 있는 Vspackage를 만드는 메커니즘 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 서비스 모델을 사용 하 여.  
  
## 단원 내용  
 [시작](../../extensibility/internals/getting-started-with-source-control-vspackages.md)  
 소스 제어 플러그에 대 한 소스 제어 기능을 구현 하는 데는 고급 대신 소스 제어 패키지를 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [아키텍처](../../extensibility/internals/source-control-vspackage-architecture.md)  
 다이어그램을 제공 하 고 소스 제어 패키지의 구성 요소에 설명 합니다.  
  
 [기능](../../extensibility/internals/source-control-vspackage-features.md)  
 소스 제어 패키지의 다양 한 기능에 설명 합니다.  
  
 [디자인 요소](../../extensibility/internals/source-control-vspackage-design-elements.md)  
 소스 제어 패키지에 통합 되어 구현 해야 Vspackage의 구조를 설명 합니다.  
  
## 관련 단원  
 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)  
 소스 제어 기능을 제공 하는 소스 제어 플러그 인을 만드는 방법에 설명의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어 사용자 인터페이스 \(UI\)입니다.  
  
 [소스 제어](../../extensibility/internals/source-control.md)  
 소스 제어의 통합된 기능을 구현 하기 위한 옵션에 설명 합니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].