---
title: "&lt;update&gt; 요소(Visual Studio에서 Office 개발) | Microsoft Docs"
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
  - "update 요소"
  - "<update> 요소"
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발], <update> 요소"
ms.assetid: bdd5dbf7-ddda-4ef6-9db5-1fb4405261a0
caps.latest.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 24
---
# &lt;update&gt; 요소(Visual Studio에서 Office 개발)
  `update` 요소는 솔루션에서 업데이트를 확인하는 간격을 지정합니다.  
  
## 구문  
  
```  
<update  
  enabled>  
  <expiration  
    maximumAge  
    unit  
  />  
</update>  
```  
  
## 요소 및 특성  
 `update` 요소는 필수 요소이며 `vstav3` 네임스페이스에 포함되어 있습니다.  
  
 `update` 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 요소.  enabled는 다음 값 중 하나로 설정합니다.<br /><br /> -   **true** \- 업데이트를 확인합니다.<br />-   **false** \- 업데이트를 확인하지 않습니다.|  
  
 `update` 요소에는 다음과 같은 자식 요소가 있습니다.  
  
### expiration  
 `expiration` 요소는 필수 요소이며 `vstav3` 네임스페이스에 포함되어 있습니다.  이 요소는 솔루션에서 업데이트를 확인하는 간격을 지정합니다.  
  
 `expiration` 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`maximumAge`|-   필수 요소.  이 값은 정수로 설정합니다.|  
|`unit`|필수 요소.  `unit`은 다음 값 중 하나로 설정합니다.<br /><br /> -   **hours**<br />-   **days**<br />-   **weeks**|  
  
## 업데이트를 항상 확인하는 예제  
  
### 설명  
 다음 코드 예제에서는 Office 솔루션에서 항상 업데이트를 확인하도록 설정된 `update` 요소를 보여 줍니다.  
  
### 코드  
  
```  
<vstav3:update enabled="true" />  
```  
  
## 기본 업데이트 간격을 설정하는 예제  
  
### 설명  
 다음 코드 예제에서는 Office 솔루션에 대한 응용 프로그램 매니페스트의 `update` 요소를 보여 줍니다.  이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공되는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstav3:update enabled="true">  
    <vstav3:expiration maximumAge="7" unit="days" />  
</vstav3:update>  
```  
  
## 참고 항목  
 [ClickOnce를 사용하여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)  
  
  