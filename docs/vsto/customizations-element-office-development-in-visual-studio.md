---
title: "&lt;customizations&gt; 요소(Visual Studio에서 Office 개발)"
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
  - "<customizations> 요소"
  - "customizations 요소"
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발], <customizations> 요소"
ms.assetid: fe1133ef-5fdf-4945-a67b-55a66a4e2109
caps.latest.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# &lt;customizations&gt; 요소(Visual Studio에서 Office 개발)
  `vstov4` 네임스페이스의 `customizations` 요소에는 각 Office 솔루션 설치 및 로드에 대한 모든 정보가 포함됩니다.  
  
## 문서 수준 사용자 지정에 대한 구문  
  
```  
<customizations> <customization id <document solutionId /> </customization> </customizations>  
```  
  
## VSTO 추가 기능에 대한 구문  
  
```  
<customizations> <customization id <appAddin application loadBehavior keyName> <friendlyName></friendlyName> <description></description> <formRegions></formRegions> </customization> </customizations>  
```  
  
## 요소 및 특성  
 `customizations` 요소에는 각 Office 솔루션에 대한 특정 정보가 포함됩니다. 이 요소는 `vstov4=urn:schemas-microsoft-com:vsto.v4` 네임스페이스에 있어야 합니다. 어셈블리의 자식 요소도 이 네임스페이스에 있어야 합니다.  
  
 `customizations` 요소에는 특성이 없습니다.  
  
 `customizations` 요소에는 다음 자식 요소가 있습니다.  
  
### 사용자 지정  
 필수 요소.`vstov4` 네임스페이스에서 `customization` 요소는 [&#60;customization&#62; 요소&#40;Visual Studio에서 Office 개발&#41;](../vsto/customization-element-office-development-in-visual-studio.md)에 정의되어 있습니다.  
  
## 문서 수준 사용자 지정 예제  
  
### 설명  
 다음 코드 예제에서는 문서 수준 사용자 지정의 `customizations` 요소를 보여 줍니다.  
  
> [!NOTE]  
>  이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstov4:customizations xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4"> <vstov4:customization> <vstov4:document solutionId="73e" /> </vstov4:customization> </vstov4:customizations>  
```  
  
## VSTO 추가 기능의 예제  
  
### 설명  
 다음 코드 예제에서는 VSTO 추가 기능의 `customizations` 요소를 보여 줍니다. 양식 영역을 포함하는 Outlook VSTO 추가 기능입니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstov4:customizations xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4"> <vstov4:customization> <vstov4:appAddIn application="Outlook" loadBehavior="3" keyName="ContosoOutlookAddIn"> <vstov4:friendlyName> ContosoOutlookAddIn </vstov4:friendlyName> <vstov4:description> ContosoOutlookAddIn - Outlook VSTO Add-in created with Visual Studio Tools for Office </vstov4:description> <vstov4:formRegions> <vstov4:formRegion name="OutlookAddIn1.FormRegion1"> <vstov4:messageClass name="IPM.Note" /> <vstov4:messageClass name="IPM.Contact" /> <vstov4:messageClass name="IPM.Appointment" /> </vstov4:formRegion> </vstov4:formRegions> </vstov4:appAddIn> </vstov4:customization> </vstov4:customizations>  
```  
  
## 참고 항목  
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)  
  
  