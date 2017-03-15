---
title: "MSBuild 오류 MSB3154 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateBootstrapper.ProductCultureNotFound"
helpviewer_keywords: 
  - "MSB3154"
ms.assetid: 513b70fa-15f5-4137-bdbc-5974607fb75a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3154
**MSB3154: '\<package\>' 항목에 대한 문자열 리소스를 찾을 수 없습니다.**  
  
 이 오류는 지정된 패키지에 어떠한 문화권 관련 정보도 들어 있지 않은 경우 발생합니다.  package.xml 파일이 없거나 이 파일에 `Culture` 특성이 포함되어 있지 않습니다.  
  
### 이 오류를 해결하려면  
  
-   올바른 `Culture` 태그가 포함된 유효한 package.xml을 제공합니다.