---
title: "MSBuild 오류 MSB3144 | Microsoft Docs"
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
  - "MSBuild.GenerateBootstrapper.InvalidInput"
helpviewer_keywords: 
  - "MSB3144"
ms.assetid: 955e0db3-afe2-4c03-8e95-3419878374df
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3144
**MSB3144: 부트스트래퍼를 생성하는 데 필요한 데이터가 충분하지 않습니다.  'ApplicationFile' 또는 'BootstrapperItems' 매개 변수 중 적어도 하나에 대한 값을 지정하십시오.**  
  
 이 오류는 부트스트래퍼를 생성하는 데 필요한 데이터를 충분히 제공하지 않은 경우 발생합니다.  빌드 프로세스에서 응용 프로그램 설치 관리자와 패키지가 없는 빈 부트스트래퍼가 생성됩니다.  
  
### 이 오류를 해결하려면  
  
-   `ApplicationFile` 또는 `BootstrapperItems` 매개 변수 중 적어도 하나에 대한 값을 제공합니다.  
  
## 참고 항목  
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)