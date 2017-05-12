---
title: "&lt;formRegion&gt; 요소(Visual Studio에서 Office 개발)"
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
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발], <formRegion> 요소"
ms.assetid: d397cf31-c0ef-47f0-860a-cd816e4bf6eb
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 19
---
# &lt;formRegion&gt; 요소(Visual Studio에서 Office 개발)
  `vstov4`  네임스페이스의 `formRegion` 요소는 VSTO 추가 기능과 관련된 Microsoft Office Outlook 양식 영역을 식별합니다.  
  
## 구문  
  
```  
<formRegion  
  name>  
  <messageClass  
    name/>  
</formRegion>  
```  
  
## 요소 및 특성  
 `vstov4` 네임스페이스의 `formRegion` 요소는 Outlook VSTO 추가 기능과 관련된 양식 영역을 식별합니다. 양식 영역을 포함하는 Outlook VSTO 추가 기능에만 필요합니다.  
  
 단일 VSTO 추가 기능에 대해 `formRegions` 요소 내에 정의된 여러 `formRegion` 요소가 있을 수 있습니다.  
  
 `formRegion` 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`name`|필수 요소. 양식 영역 이름을 식별합니다.|  
  
 `formRegion` 요소에는 다음 자식 요소가 있습니다.  
  
### messageClass  
 `messageClass`  요소는 양식 영역과 관련된 Outlook 양식을 식별합니다.  
  
 `messageClass` 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`name`|필수 요소. 양식 영역과 관련된 양식을 식별합니다.|  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]을 사용하여 배포된 Outlook VSTO 추가 기능에 대한 응용 프로그램 매니페스트의 `formRegion` 요소를 보여 줍니다. 이 양식 영역과 관련된 세 개의 메시지 클래스가 있습니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
```  
<vstov4:formRegion name="OutlookAddIn1.FormRegion1"> <vstov4:messageClass name="IPM.Note" /> <vstov4:messageClass name="IPM.Contact" /> <vstov4:messageClass name="IPM.Appointment" /> </vstov4:formRegion>  
```  
  
## 참고 항목  
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)  
  
  