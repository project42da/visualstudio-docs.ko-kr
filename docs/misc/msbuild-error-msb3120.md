---
title: "MSBuild 오류 MSB3120 | Microsoft Docs"
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
  - "GenerateManifest.FileAssociationExtensionTooLong"
helpviewer_keywords: 
  - "MSB3120"
ms.assetid: 20bc64f5-aadc-4eec-9915-a87a3d7f81ea
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3120
**MSB3120: 파일 연결 확장명 '\<extension\>'이 허용되는 최대 길이인 \<maximumlength\>를 초과합니다.**  
  
 파일 연결 확장명의 문자 수는 지정된 숫자를 초과할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md) `extension` 특성을 대상 운영 체제에 허용되는 한도 내의 문자를 포함하는 값으로 설정합니다.  
  
## 참고 항목  
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)