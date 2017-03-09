---
title: "MSBuild 오류 MSB3163 | Microsoft Docs"
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
  - "MSBuild.GenerateBootstrapper.InvalidComponentsLocation"
helpviewer_keywords: 
  - "MSB3163"
ms.assetid: 35c5efbf-2fd7-478c-bb8e-3c4eabb3e4d4
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3163
**MSB3163: 빌드 입력 매개 변수 'ComponentsLocation\='\<ComponentsLocation\>'이\(가\) 잘못되었습니다.  이 값은 'HomeSite', 'Relative' 또는 'Absolute' 중 하나여야 합니다.  'HomeSite'를 기본값으로 사용합니다.**  
  
 이 오류는 `ComponentsLocation` 속성\(필수 구성 요소가 설치되는 위치\)에 대해 지정한 값이 잘못된 경우 발생합니다.  `ComponentsLocation`의 값은 `HomeSite`, `Relative` 또는 `Absolute` 중 하나여야 합니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)