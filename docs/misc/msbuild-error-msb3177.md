---
title: "MSBuild 오류 MSB3177 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.AllowPartiallyTrustedCallers"
helpviewer_keywords: 
  - "MSB3177"
ms.assetid: 0b2417d5-3bc3-4169-b69c-a4a3cbf47882
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3177
**MSB3177: '\<reference\>' 참조에는 부분적으로 신뢰할 수 있는 호출자를 사용할 수 없습니다.**  
  
 이 경고는 응용 프로그램이 부분적으로 신뢰할 수 있는 응용 프로그램이고 *reference*가 프로젝트 참조로 추가되었으며 강력한 이름이 지정되어 있지만 APTCA 특성이 없는 경우 응용 프로그램 매니페스트를 생성하는 과정에서 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   참조된 어셈블리에 APTCA 특성을 추가합니다. 이를 추가할 수 없는 경우 이 특성의 사용을 중지합니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)