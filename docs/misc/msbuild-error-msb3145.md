---
title: "MSBuild 오류 MSB3145 | Microsoft Docs"
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
  - "MSBuild.GenerateBootstrapper.InvalidUrl"
helpviewer_keywords: 
  - "MSB3145"
ms.assetid: 183d4e7e-bdc6-402f-a1b6-531505be605f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3145
**MSB3145: 빌드 입력 매개 변수 '\<property\>\=\<value\>'은\(는\) 웹 URL 또는 UNC 공유가 아닙니다.**  
  
 이 오류는 `SupportUrl`, `ComponentsUrl` 또는 `ApplicationUrl` 프로젝트 속성의 값이 유효하지 않은 경우 발생합니다.  이 값은 유효한 URI 또는 UNC 경로여야 합니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)