---
title: "방법: 시작 키트 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "시작 키트, 만들기"
ms.assetid: ed7d1844-7c01-424a-a831-5003efe0f7bc
caps.latest.revision: 22
caps.handback.revision: 22
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 방법: 시작 키트 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

시작 키트에는 완전한 응용 프로그램 코드 및 응용 프로그램을 수정하거나 확장하는 방법에 대한 설명서가 포함되어 있습니다.  시작 키트를 만드는 작업은 근본적으로 일반 프로젝트 템플릿을 만드는 것과 같으며, 차이점은 시작 키트를 기반으로 하는 프로젝트가 만들어질 때 열리도록 설정된 설명서 파일이 시작 키트에 포함되어 있다는 것뿐입니다.  
  
## 시작 키트 디자인 및 개발  
 우선 개발하려는 시작 키트의 형식을 확인하고 대상을 정의합니다.  다음 자신의 목표에 맞게 프로젝트와 설명서를 디자인합니다.  
  
 샘플 응용 프로그램이나 플러그 인을 만드는 경우  
  
-   오류 없이 빌드되는 프로젝트를 만듭니다.  
  
-   템플릿 코드를 추가하여 추가 작업을 구현합니다\(선택적\).  
  
-   설명서를 준비합니다.  
  
 학습 도구를 만드는 경우  
  
-   오류 없이 빌드되는 프로젝트를 만듭니다.  
  
-   코드 조각과 항목 템플릿 같은 리소스를 구성합니다.  
  
-   설명서를 준비합니다.  
  
## 템플릿 만들기  
 프로젝트와 설명서를 완성했으면 시작 키트에 대한 프로젝트 템플릿을 만들 수 있습니다.  이 프로세스는 프로젝트 템플릿을 만드는 것과 똑같습니다.  
  
 다음 항목에는 템플릿 만들기에 대한 정보가 포함되어 있습니다.  
  
 [방법: 프로젝트 템플릿 만들기](../ide/how-to-create-project-templates.md)  
 **템플릿 내보내기** 마법사를 사용하여 템플릿을 만드는 방법을 설명합니다.  
  
 [방법: 기존 템플릿 업데이트](../ide/how-to-update-existing-templates.md)  
 내보낸 템플릿을 편집하는 방법을 설명합니다.  이 프로시저를 사용하면 .vstemplate 파일을 수정하여 시작 키트를 사용자 지정할 수 있습니다.  
  
## 참고 항목  
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)   
 [템플릿 사용자 지정](../ide/customizing-project-and-item-templates.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)