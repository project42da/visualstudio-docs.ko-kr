---
title: "&lt;document&gt; 요소(Visual Studio에서 Office 개발)"
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
  - "document 요소"
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발], <document>요소"
  - "<document>요소"
ms.assetid: b4525a0e-8a03-4881-a3e2-8cc019029071
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt;document&gt; 요소(Visual Studio에서 Office 개발)
  `vstov4` 네임스페이스의 `document` 요소에는 문서 수준 사용자 지정의 사용자 지정 관련 정보가 저장됩니다.  
  
## 구문  
  
```  
<document solutionId />  
```  
  
## 요소 및 특성  
 문서 수준 사용자 지정의 경우에만 필수 요소입니다.  `document` 요소는 `vstov4` 네임스페이스에 포함되어 있습니다.  `document` 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`solutionId`|필수 요소.  Visual Studio도구 Office런타임사용 하 여 문서 수준솔루션을 고유 하 게 식별 하는 데 사용 되는 GUID입니다.  이 값은 \_AssemblyLocation 사용자 지정 문서 속성으로 저장됩니다.  자세한 내용은 [사용자 지정 문서 속성 개요](../vsto/custom-document-properties-overview.md)를 참조하십시오.|  
  
 `document`에는 자식 요소가 없습니다.  
  
## 문서 수준 사용자 지정 예제  
  
### 설명  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]를 사용하여 배포되는 문서 수준 Office 솔루션의 `document` 요소를 보여 줍니다.  이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공되는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstov4:document   
  solutionId="73e" />  
```  
  
## 참고 항목  
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)  
  
  