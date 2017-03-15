---
title: "MSBuild 오류 MSB3123 | Microsoft Docs"
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
  - "GenerateManifest.FileAssociationsCountExceedsMaximum"
helpviewer_keywords: 
  - "MSB3123"
ms.assetid: 343aa8a8-9ab9-4dd5-be59-8eccf1f3c012
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3123
**MSB3123: 파일 연결 수가 한계인 \<limit\>를 초과합니다.**  
  
 각 파일에는 고정된 개수의 파일 확장명만 연결할 수 있습니다.  이 오류는 대상 운영 체제에 허용되는 수보다 많은 파일 확장명을 연결하려고 할 때 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   파일 연결 수를 지정된 수로 제한합니다.  
  
## 참고 항목  
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)