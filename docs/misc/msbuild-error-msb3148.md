---
title: "MSBuild 오류 MSB3148 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateBootstrapper.NoOutputPath"
helpviewer_keywords: 
  - "MSB3148"
ms.assetid: 389b335f-5760-4dcc-9146-c52d6d7ac81f
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3148
**MSB3148: 빌드 설정에 출력 경로를 지정하지 않았습니다.**  
  
 이 오류는 출력 경로를 null로 지정하거나 잘못 지정한 경우 발생합니다. 프로젝트 파일에서 `OutputPath=""`를 지정한 경우를 예로 들 수 있습니다.  출력 경로의 기본값은 `CurrentDirectory`입니다.  
  
### 이 오류를 해결하려면  
  
-   `OutputPath`가 비어 있거나 프로젝트 파일에 포함되어 있지 않은지 확인합니다.  
  
## 참고 항목  
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)