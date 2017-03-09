---
title: "VSPackage 상태 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "상태, VSPackage"
  - "VSPackage, 응용 프로그램 상태 관리"
  - "상태 지속성"
ms.assetid: 6056a9ea-e7a8-481c-9fc8-340229fa12d9
caps.latest.revision: 25
caps.handback.revision: 25
manager: "douge"
---
# VSPackage 상태
집합을 유지 된 값 또는 상태를 결정 하는 여러 가지 요인에는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 응용 프로그램입니다.  
  
-   프로젝트 프로젝트 구성 속성에 있습니다.  
  
-   솔루션 속성에 있습니다.  
  
-   사용자 설정 크기 및 문서 창, 도구 창, 도킹 상태 및 바로 가기 키의 위치를 결정합니다.  
  
-   응용 프로그램 사용자가 설정 하는 옵션을 가질 수 있습니다.  
  
-   응용 프로그램에서 만든 개체 자체의 속성을 가질 수 있습니다.  
  
 몇 가지 방법 중에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 응용 프로그램 상태를 관리할 수 있습니다.  
  
-   프로젝트 및 솔루션 속성 페이지에서 있습니다.  
  
-   통해 해당  **가져오기 및 내보내기 마법사**, 사용자 설정이 한 컴퓨터에서 다른 이동 수 있습니다.  
  
-   통해는  **옵션** 응용 프로그램에 관련 된 옵션을 포함 하는 대화 상자입니다.  
  
-   통해는  **속성이** 개체의 속성을 표시 하는 창입니다.  
  
-   자동화를 통해.  응용 프로그램 자동화를 제공 되었습니다 VSPackage 및 개체 속성에 액세스할 수 있습니다.  
  
 원본으로 사용 하는 응용 프로그램 상태는 응용 프로그램 상태를 저장 하 고 복원할 수 있도록 다양 한 지 속성 메커니즘입니다.  
  
## 단원 내용  
 [상태 지속성 지원](../misc/support-for-state-persistence.md)  
 저장, 복원 및 있는 Vspackage의 상태를 다시 설정 하는 방법에 대 한 일반적인 전략을 보여 줍니다.  
  
 [옵션 및 옵션 페이지](../extensibility/internals/options-and-options-pages.md)  
 일반 및 사용자 지정 옵션 페이지를 소개 하 고이 구현 하는 방법에 설명 합니다.  
  
 [옵션 페이지 만들기](../extensibility/creating-an-options-page.md)  
 옵션 페이지, 간단한 페이지와 사용자 지정 페이지를 만드는 방법에 설명 합니다.  
  
 [설정 범주에 대한 지원](../misc/support-for-settings-categories.md)  
 사용자 설정 및 어떻게 작성 하 고 유지 하는 방법에 대해 설명 합니다.  
  
 [설정 범주 만들기](../extensibility/creating-a-settings-category.md)  
 만드는 방법에 설명에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설정 범주 값을 저장 하 고 값 설정 파일에서 복원 하는 데 사용 합니다.  
  
 [속성 및 속성 창 확장](../extensibility/extending-properties-and-the-property-window.md)  
 표시 하 고 있는 개체의 값을 변경 하는 방법에 설명의  **속성이** 창.  
  
 [속성 창에 속성 노출](../extensibility/exposing-properties-to-the-properties-window.md)  
 개체의 공용 속성을 노출 하는 방법에 설명의  **속성이** 창입니다.  
  
 [프로젝트 및 구성 속성에 대 한 지원](../extensibility/internals/support-for-project-and-configuration-properties.md)  
 표시 하 고 구성 하 고 프로젝트 속성을 변경 하는 방법에 설명 합니다.  
  
 [프로젝트 속성 가져오기](../extensibility/getting-project-properties.md)  
 도구 창에서 프로젝트 속성을 표시 하는 관리 되는 Vspackage를 만드는 과정을 안내 합니다.  
  
 [설정 저장소를 사용 하 여](../extensibility/using-the-settings-store.md)  
 보존 설정 저장소 메커니즘 및 그 사용 방법을 설명 합니다.  
  
## 관련 단원  
 [Vspackage](../extensibility/internals/vspackages.md)  
 일반 방향을 만들어 Vspackages를 사용 하는 방법에 설명 하는 항목을 제공 합니다.