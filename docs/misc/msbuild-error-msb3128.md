---
title: "MSBuild 오류 MSB3128 | Microsoft Docs"
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
  - "GenerateManifest.ManifestsSignedHashExcluded"
helpviewer_keywords: 
  - "MSB3128"
ms.assetid: e8612a4b-4016-48d2-b5f0-a1091bfe8cb1
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3128
**MSB3128: ClickOnce 매니페스트에 해시되지 않은 참조가 하나 이상 들어 있어서 서명할 수 없습니다.**  
  
 서명된 매니페스트가 있는 응용 프로그램을 게시할 때는 모든 파일이 해시에 포함되어야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  **프로젝트 디자이너**의 **게시** 페이지로 이동합니다.  
  
2.  **응용 프로그램 파일**을 클릭합니다.  
  
3.  게시할 모든 파일에 대해 **해시** 값을 **포함**으로 설정합니다.  
  
## 참고 항목  
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)