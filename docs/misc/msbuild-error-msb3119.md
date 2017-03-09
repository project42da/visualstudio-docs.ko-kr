---
title: "MSBuild 오류 MSB3119 | Microsoft Docs"
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
  - "GenerateManifest.FileAssociationExtensionMissingLeadDot"
helpviewer_keywords: 
  - "MSB3119"
ms.assetid: 52d68b0e-01d4-436f-a96c-733fd20a8c04
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3119
**MSB3119: 파일 연결 확장명은 마침표 문자\(.\)로 시작해야 합니다.**  
  
 이 오류는 파일 연결을 구성했는데 확장명이 마침표 문자\(.\)로 시작하지 않는 경우에 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md) `extension` 특성을 ".doc"와 같이 마침표 문자\(.\)로 시작하는 값으로 설정합니다.  
  
## 참고 항목  
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)