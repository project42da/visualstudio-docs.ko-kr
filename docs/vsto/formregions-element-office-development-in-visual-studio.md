---
title: "&lt;formRegions&gt; 요소(Visual Studio에서 Office 개발) | Microsoft Docs"
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
  - "formRegions 요소"
  - "<formRegions> 요소"
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발], <formRegions> 요소"
ms.assetid: 71faa2da-9d38-43e8-9d7d-0bcd944ef9a3
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 22
---
# &lt;formRegions&gt; 요소(Visual Studio에서 Office 개발)
  `vstov4`  네임스페이스의 `formRegions` 요소에는 VSTO 추가 기능과 관련된 영역의 Microsoft Office Outlook 양식이 포함됩니다.  
  
## 구문  
  
```  
<formRegions>  
  <formRegion>  
  </formRegion>  
</formRegions>  
```  
  
## 요소 및 특성  
 `vstov4`  네임스페이스의 `formRegions` 요소에는 Outlook VSTO 추가 기능에 대한 모든 `formRegion` 요소가 포함됩니다. 양식 영역을 포함하는 Outlook VSTO 추가 기능에만 필요합니다.  
  
 하나의 응용 프로그램 매니페스트에서는 하나의 `formRegions` 요소만 정의할 수 있습니다.  
  
 `formRegions` 요소에는 특성이 없습니다.  
  
 `formRegions` 요소에는 다음 요소가 있습니다.  
  
### formRegion  
 양식 영역을 포함하는 Outlook VSTO 추가 기능에 필요합니다.`formRegion` 요소는 [&#60;formRegion&#62; 요소&#40;Visual Studio에서 Office 개발&#41;](../vsto/formregion-element-office-development-in-visual-studio.md)에 정의되어 있습니다.  
  
## VSTO 추가 기능 예제  
  
### 설명  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]을 사용하여 배포된 응용 프로그램 수준의 Office 솔루션에 대한 응용 프로그램 매니페스트의 `formRegions` 요소를 보여 줍니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstov4:formRegions> <vstov4:formRegion name="OutlookAddIn1.FormRegion1"> <vstov4:messageClass name="IPM.Note" /> <vstov4:messageClass name="IPM.Contact" /> <vstov4:messageClass name="IPM.Appointment" /> </vstov4:formRegion> </vstov4:formRegions>  
```  
  
## 참고 항목  
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)  
  
  