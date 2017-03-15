---
title: "MSBuild 오류 MSB3149 | Microsoft Docs"
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
  - "MSBuild.GenerateBootstrapper.NoResources"
helpviewer_keywords: 
  - "MSB3149"
ms.assetid: 63857405-d420-457d-9ba7-80e1a2a9dcb7
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3149
**MSB3149: 부트스트래퍼를 빌드하는 데 사용할 수 있는 리소스가 없습니다.**  
  
 이 오류는 임의의 culture에 일치하는 부트스트래퍼 리소스 파일\(setup.xml\)을 찾을 수 없는 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   **제어판**에서 **프로그램 추가\/제거**를 선택하고 Visual Studio SDK를 복구하거나 파일을 적절한 디렉터리\(\<SDK 설치 경로\>\\bootstrapper\\engine\\\<문화권\>\\setup.xml\)로 복사합니다.  
  
## 참고 항목  
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)