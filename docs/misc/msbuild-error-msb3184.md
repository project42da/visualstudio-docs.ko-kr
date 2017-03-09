---
title: "MSBuild 오류 MSB3184 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.InvalidInputManifest"
helpviewer_keywords: 
  - "MSB3184"
ms.assetid: 2be9f8e9-04ee-4299-b79f-965ee57a1a34
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3184
**MSB3184: 입력 매니페스트가 잘못되었습니다.**  
  
 이 오류는 응용 프로그램 매니페스트나 배포 매니페스트가 포함된 것으로 예상되는 파일을 빌드 프로세스에서 로드하려 하지만 실제로는 이 파일에 다른 매니페스트나 손상된 데이터 같이 다른 내용이 포함된 것으로 판명되는 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   프로젝트의 매니페스트가 유효하고 적절한지 확인합니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)