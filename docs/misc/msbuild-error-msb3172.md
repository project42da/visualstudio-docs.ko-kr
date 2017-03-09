---
title: "MSBuild 오류 MSB3172 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.ReadInputManifestFailed"
helpviewer_keywords: 
  - "MSB3172"
ms.assetid: aa7291db-1f36-41e7-a510-90cd4daaa89d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3172
**MSB3172: '\<file\>' 매니페스트를 읽을 수 없습니다. '  \<error\>'**  
  
 이 오류는 빌드 프로세스에서 매니페스트 파일을 읽는 동안 일반적인 문제를 발견한 경우 발생합니다.  이 오류 메시지에는 파일 이름이 표시되고 문제에 대한 더 구체적인 정보가 함께 제공됩니다.  
  
 어셈블리나 매니페스트 파일을 콘텐츠 파일로 추가했을 수 있습니다.  종속 어셈블리가 프로젝트 시스템에서 제대로 참조될 수 있도록 **파일 추가** 대신 **참조 추가** 명령을 사용해야 합니다.  좀 더 복잡한 프로젝트에서는 일반적으로 bin 폴더에 있는 .exe.manifest가 프로젝트 파일로 표시되지만 이대로 두면 안 됩니다.  숨겨진 app.manifest 파일은 .exe.manifest 파일이 되며 고급 시나리오에서 수동으로 편집할 수 있습니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)