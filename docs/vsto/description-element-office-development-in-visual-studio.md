---
title: "&lt;description&gt; 요소(Visual Studio에서 Office 개발)"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "description 요소"
  - "<description> 요소"
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발], <description> 요소"
ms.assetid: 27c90f8c-393d-4557-9371-2e4e3c4a2d95
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# &lt;description&gt; 요소(Visual Studio에서 Office 개발)
  `vstov4`  네임스페이스의 `description` 요소는 Microsoft Office 응용 프로그램의 COM 추가 기능 대화 상자에 나타나는 Office 솔루션에 대한 설명을 저장합니다.  
  
## 구문  
  
```  
<description>  
</description>  
```  
  
## 요소 및 특성  
 선택 사항입니다.`description` 요소는 `vstov4`  네임스페이스에 있습니다. Microsoft Office 응용 프로그램의 COM 추가 기능 대화 상자에 표시되는 추가 기능에 대한 설명이 포함됩니다.  
  
 `description` 요소에는 특성 또는 요소가 없습니다.  
  
## VSTO 추가 기능 예제  
  
### 설명  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]를 사용하여 배포된 응용 프로그램 수준 솔루션의 `description` 요소를 보여 줍니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstov4:description> ContosoOutlookAddIn - Outlook add-in created with Visual Studio Tools for Office </vstov4:description>  
```  
  
## 참고 항목  
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)  
  
  