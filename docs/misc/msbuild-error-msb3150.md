---
title: "MSBuild 오류 MSB3150 | Microsoft Docs"
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
  - "MSBuild.GenerateBootstrapper.NoStringsForCulture"
helpviewer_keywords: 
  - "MSB3150"
ms.assetid: 90d86aef-f4df-4070-8ecc-173eb40668aa
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3150
**MSB3150: 문화권이 '{0}'인 부트스트래퍼를 빌드하는 데 사용할 수 있는 문자열 리소스가 없습니다.**  
  
 이 오류는 setup.xml을 찾았지만 이 파일에 문자열 노드가 포함되어 있지 않은 경우 발생합니다.  XML 파일이 손상되었을 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   **제어판**에서 **프로그램 추가\/제거**를 선택하고 Visual Studio SDK를 복구하거나 파일을 적절한 디렉터리\(\<SDK 설치 경로\>\\bootstrapper\\engine\\\<문화권\>\\setup.xml\)로 복사합니다.