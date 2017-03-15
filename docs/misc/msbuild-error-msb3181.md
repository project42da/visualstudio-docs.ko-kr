---
title: "MSBuild 오류 MSB3181 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.DuplicateTargetPath"
helpviewer_keywords: 
  - "MSB3181"
ms.assetid: 49349fc2-3fa1-470d-a5cb-6ad72b93f408
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3181
**MSB3181: 대상 경로 '\<path\>'이\(가\) 동일한 파일이 두 개 이상 있습니다.**  
  
 이 경고는 응용 프로그램 매니페스트를 생성하는 동안 두 개 이상의 참조된 어셈블리 또는 파일에서 동일한 대상 경로를 공유하는 경우 발생합니다.  이 경로는 파일 이름을 포함하며 이러한 모든 어셈블리는 배포 시 서로를 덮어씁니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)