---
title: "MSBuild 오류 MSB3175 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.InvalidItemValue"
helpviewer_keywords: 
  - "MSB3175"
ms.assetid: c157e934-e4e6-43d9-abdf-cb4fb03be494
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3175
**MSB3175: '\<build task\>' 항목의 '\<file\>'에 사용할 수 없는 값입니다.**  
  
 이 경고는 `AssemblyType`, `DependencyType`, `FileType` 또는 `TargetZone` 같이 다양한 열거형 기반 작업 항목 속성의 값을 빌드 프로세스에서 인식할 수 없는 경우 발생합니다.  이는 응용 프로그램 매니페스트와 배포 매니페스트에 모두 해당합니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)