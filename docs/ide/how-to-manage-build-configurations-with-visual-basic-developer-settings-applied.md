---
title: "방법: Visual Basic 개발자 설정을 적용하여 빌드 구성 관리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "고급 빌드 구성"
  - "Visual Basic 개발자 설정을 사용하여 빌드"
  - "디버그 빌드"
  - "MSBuild, 디버그 빌드"
  - "MSBuild, 릴리스 빌드"
  - "릴리스 빌드"
  - "Visual Studio, Visual Basic 설정을 사용하여 빌드"
ms.assetid: eaea6e0b-6c61-4869-8d63-d372c745a23c
caps.latest.revision: 9
caps.handback.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 방법: Visual Basic 개발자 설정을 적용하여 빌드 구성 관리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

기본적으로 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 개발자 설정이 적용될 때는 모든 고급 빌드 구성 옵션이 숨겨집니다.  이 항목에서는 이러한 설정을 수동으로 활성화하는 방법을 설명합니다.  
  
## 고급 빌드 구성 활성화  
 기본적으로 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 개발자 설정에서는 **구성 관리자** 대화 상자를 여는 옵션과 [프로젝트 디자이너](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)의 **구성** 및 **플랫폼** 목록을 숨깁니다.  
  
#### 고급 빌드 구성을 활성화하려면  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  **프로젝트 및 솔루션**을 확장한 다음 **일반**을 클릭합니다.  
  
    > [!NOTE]
    >  **일반** 노드는 **모든 설정 표시** 옵션을 선택하지 않아도 표시됩니다.  사용 가능한 모든 옵션을 보려면 **모든 설정 표시**를 클릭합니다.  
  
3.  **고급 빌드 구성 표시**를 클릭합니다.  
  
4.  **확인**을 클릭합니다.  
  
     **빌드** 메뉴에서 이제 **구성 관리자**를 사용할 수 있으며 **구성** 및**플랫폼** 목록이 프로젝트 디자이너에 표시됩니다.  
  
## 참고 항목  
 [빌드 구성 이해](../ide/understanding-build-configurations.md)   
 [Visual Studio에서 응용 프로그램　빌드](../ide/compiling-and-building-in-visual-studio.md)