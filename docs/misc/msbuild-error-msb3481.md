---
title: "MSBuild 오류 MSB3481 | Microsoft Docs"
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
  - "MSBuild.SignFile.CertNotInStore"
helpviewer_keywords: 
  - "MSB3481"
ms.assetid: 55f99775-3bd5-4e1b-b184-c6405d75e8ff
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3481
**MSB3481: 서명 인증서를 찾을 수 없습니다.  인증서가 현재 사용자의 개인 저장소에 있는지 확인하십시오.**  
  
 이 오류는 사용자의 개인 인증서 저장소에서 서명 인증서를 찾지 못한 경우 발생합니다.  이 오류는 인증서를 찾았지만 인증서가 일치하지 않음을 의미하는 [MSBuild 오류 MSB3486](../misc/msbuild-error-msb3486.md)과 비슷합니다.  
  
### 이 오류를 해결하려면  
  
-   프로젝트의 .pfx 파일에 일치하는 유효한 인증서가 개인 인증서 저장소에 있는지 확인합니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)