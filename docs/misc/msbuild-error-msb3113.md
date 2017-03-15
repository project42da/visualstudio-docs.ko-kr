---
title: "MSBuild 오류 MSB3113 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.ResolveFailedInReadWriteMode"
helpviewer_keywords: 
  - "MSB3113"
ms.assetid: 81e73738-e6ee-4651-9f48-acb1feef3ff5
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3113
**MSB3113: '\<file\>' 파일을 찾을 수 없습니다.**  
  
 이 오류는 새 매니페스트를 만들 때 확인할 수 없는 참조가 발견되면 발생합니다.  프로젝트 파일이나 작업 매개 변수에 문제가 있는 경우일 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   프로젝트 파일에서 파일 참조가 충돌하는지 확인합니다. 사용자 지정 빌드 작업을 수행하는 경우 빌드 매개 변수도 확인합니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)