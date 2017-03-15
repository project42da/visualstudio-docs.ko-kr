---
title: "MSBuild 오류 MSB3124 | Microsoft Docs"
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
  - "GenerateManifest.FileAssociationsDuplicateExtensions"
helpviewer_keywords: 
  - "MSB3124"
ms.assetid: d8365103-aa9d-400e-9c24-0a43e2bfbd14
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3124
**MSB3124: 확장명 '\<extensionname\>'에 대한 파일 연결을 이미 만들었습니다.**  
  
 이 오류는 파일 연결 확장명이 중복될 때 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   고유하지 않은 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md) `extension` 특성을 제거합니다.  목록에 있는 각 \<fileAssociation\> 요소의 확장명 특성은 고유해야 합니다.  
  
## 참고 항목  
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)