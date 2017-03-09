---
title: "프로젝트 형식을 사용할 수 없음 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.projecttypenotavailable"
helpviewer_keywords: 
  - "프로젝트 형식을 사용할 수 없음 오류"
ms.assetid: a579fe75-efa2-4dd0-b5d7-ae106d3aedbd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 프로젝트 형식을 사용할 수 없음
"'\<project\>'을\(를\) 열 수 없습니다. 이 응용 프로그램 버전에서 지원하지 않는 프로젝트 형식\(\<project type\>\)입니다."라는 오류와 함께 이 대화 상자가 나타납니다.  
  
## 해결 방법  
  
-   이 대화 상자는 지정한 파일을 여는 데 필요한 제품 또는 제품 버전을 찾을 수 없는 경우 나타납니다.  설치된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전으로 열 수 없는 프로젝트 파일을 열려고 할 때 일반적으로 이 오류가 발생합니다.  예를 들어, [!INCLUDE[vbprvbxprlong](../misc/includes/vbprvbxprlong_md.md)]을 사용하여 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 프로젝트 파일을 열려고 하면 이 대화 상자가 열립니다.  
  
#### 이 오류를 해결하려면  
  
-   올바른 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 설치합니다.  
  
## 참고 항목  
 [Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드](../porting/porting-migrating-and-upgrading-visual-studio-projects.md)   
 [프로젝트 속성 참조](../ide/reference/project-properties-reference.md)