---
title: "MSBuild 오류 MSB3127 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GenerateManifest.FileAssociationDefaultIconNotInstalled"
helpviewer_keywords: 
  - "MSB3127"
ms.assetid: 161eea9a-332f-463e-a49e-d4030e937d52
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3127
**MSB3127: 기본 아이콘 \<iconname\>이 현재 파일 참조에 없거나 필요한 다운로드 그룹의 일부가 아닙니다.  기본 아이콘 파일 이름은 대\/소문자를 구분하므로 응용 프로그램 매니페스트에 참조된 파일 이름은 아이콘의 파일 이름과 정확히 일치해야 합니다.**  
  
 파일 연결을 사용하도록 구성된 응용 프로그램을 게시하는 경우 매니페스트에 참조된 기본 아이콘은 현재 파일 참조에 있거나 필요한 다운로드 그룹의 일부여야 합니다.  기본 아이콘은 구성된 파일 연결\(구성된 파일 확장명\)이 있는 파일에 표시되는 아이콘입니다.  
  
### 이 오류를 해결하려면  
  
-   아이콘 파일을 현재 프로젝트에 추가하고 필요한 다운로드 그룹에 포함합니다.  자세한 내용은 [방법: ClickOnce를 통해 게시할 파일 지정](../deployment/how-to-specify-which-files-are-published-by-clickonce.md)을 참조하십시오.  
  
## 참고 항목  
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)