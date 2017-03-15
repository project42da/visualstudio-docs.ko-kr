---
title: "MSBuild 오류 MSB3182 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.TargetPathTooLong"
helpviewer_keywords: 
  - "MSB3182"
ms.assetid: b257a206-b12b-453b-97d8-2cb9a0d3dcc9
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3182
**MSB3182: 파일 이름 '\<file\>'이\(가\) '\<length\>'자를 초과합니다.**  
  
 이 경고는 `TargetPath` 속성의 값이 너무 긴 경우 발생합니다.  이는 응용 프로그램 매니페스트와 배포 매니페스트에 모두 해당할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   `TargetPath` 속성의 값을 더 짧은 길이로 편집합니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)