---
title: "MSBuild 오류 MSB3125 | Microsoft Docs"
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
  - "GenerateManifest.FileAssociationsNoEntryPoint"
helpviewer_keywords: 
  - "MSB3125"
ms.assetid: f8a08b05-1946-4788-8577-ceefde785e95
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3125
**MSB3125: 응용 프로그램에서 파일 연결을 사용하고 있지만 EntryPoint 작성 매개 변수가 없습니다.**  
  
 이 오류는 EntryPoint 작성 매개 변수가 없는 경우에 발생합니다.  파일 연결을 사용하도록 응용 프로그램을 구성하는 경우 응용 프로그램 매니페스트에 EntryPoint 작성 매개 변수가 있어야 합니다.  \<entryPoint\> 요소는 응용 프로그램이 실행될 때 실행해야 할 어셈블리를 식별합니다.  
  
### 이 오류를 해결하려면  
  
-   [\<entryPoint\> 요소](../deployment/entrypoint-element-clickonce-application.md)를 올바른 값으로 설정합니다.  자세한 내용은 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)를 참조하십시오.  
  
## 참고 항목  
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)