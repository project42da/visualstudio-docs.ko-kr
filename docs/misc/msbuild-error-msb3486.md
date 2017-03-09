---
title: "MSBuild 오류 MSB3486 | Microsoft Docs"
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
  - "MSBuild.SignFile.CertificateError"
helpviewer_keywords: 
  - "MSB3486"
ms.assetid: 75d03d8e-3a28-4010-b602-61fe037dec74
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3486
**MSB3486: '\<certificate store\>' 저장소에서 인증서를 가져올 수 없습니다.**  
  
 이 오류는 `ResolveKeySource` MSBuild 작업 과정에서 프로젝트의 .pfx 파일 지문에 일치하는 인증서를 개인 인증서 저장소에서 찾을 수 없는 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   프로젝트의 .pfx 파일 지문이 개인 인증서 저장소에 있는 인증서의 지문과 일치하는지 확인합니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)