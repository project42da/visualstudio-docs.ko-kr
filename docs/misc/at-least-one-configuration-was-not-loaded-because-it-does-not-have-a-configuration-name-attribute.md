---
title: "At least one configuration was not loaded because it does not have a configuration name attribute | Microsoft Docs"
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
  - "vs.tasklisterror.projfile_nameless_config"
ms.assetid: 711f7253-308b-44e0-b8bc-ca5c16536a2c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# At least one configuration was not loaded because it does not have a configuration name attribute
.csproj 또는 .vbproj 파일의 각 `<Config>` 섹션에는 해당 구성의 고유 이름을 정의하는 Name 특성이 있어야 합니다.  이 진단 정보는 Name 특성이 없음을 나타냅니다.  구성에 Name 특성이 없으면 구성이 프로젝트에 로드되지 않습니다.  
  
 이 오류는 주로 프로젝트 파일을 직접 편집했을 때 발생합니다.  
  
 **이 오류를 해결하려면**  
  
-   프로젝트 파일에서 `<Config>`  줄 바로 다음에 구성 이름을 삽입합니다.  
  
    ```  
    Name = "someconfigname"  
    ```  
  
     일반적으로 사용하는 구성 이름은  `Debug` 나 `Release`입니다.  
  
## 참고 항목  
 [프로젝트 파일](/visual-cpp/ide/project-files)   
 [NIB: Project Properties \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/eb4c97ed-f667-4850-98d0-6e2a4d21bbca)