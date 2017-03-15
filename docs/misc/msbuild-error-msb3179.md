---
title: "MSBuild 오류 MSB3179 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.ComImport"
helpviewer_keywords: 
  - "MSB3179"
ms.assetid: fa744f6c-e398-4e60-b4f7-455ace7e3bd2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3179
**MSB3179: COM 참조 '\<assembly\>'을\(를\) 격리하는 동안 문제가 발생했습니다. '\<error\>'**  
  
 이는 `IsolatedComReferences` 작업 매개 변수에서 지정한 대로 응용 프로그램 매니페스트에서 RegFree COM 항목을 생성할 때 문제가 발생했음을 나타내는 일반 오류 메시지입니다.  이 오류 메시지의 뒷부분에서는 문제의 성격에 대해 더 구체적인 정보를 제공합니다.  이 오류의 가능한 원인으로는 RegFree COM 구성 요소가 빌드 컴퓨터에 올바르게 등록되지 않은 경우를 생각해 볼 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   모든 COM 구성 요소가 빌드 컴퓨터에 등록되어 있는지 확인합니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)