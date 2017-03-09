---
title: "MSBuild 오류 MSB3111 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.ConfigBindingRedirectsWithPartialTrust"
helpviewer_keywords: 
  - "MSB3111"
ms.assetid: f01286a1-ba27-4733-a431-35ffe9a31356
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3111
**MSB3111: app.config 바인딩 리디렉션을 사용하려면 완전 신뢰가 필요합니다.**  
  
 이 경고는 응용 프로그램이 해당 어셈블리 중 일부를 app.config 파일 내의 다른 버전으로 리디렉션하려 했다는 사실을 빌드 프로세스에서 발견한 경우 발생합니다.  부분적으로 신뢰할 수 있는 응용 프로그램에 대해서는 이와 같은 리디렉션을 수행할 수 없습니다.  
  
## 참고 항목  
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)