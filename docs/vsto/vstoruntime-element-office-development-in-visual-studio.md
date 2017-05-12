---
title: "&lt;vstoRuntime&gt; 요소(Visual Studio에서 Office 개발)"
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
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발], <vstoRuntime> 요소"
  - "<vstoRuntime> 요소"
  - "vstoRuntime 요소"
ms.assetid: e59a8a61-9ff2-4032-9983-4a1e289e70a7
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 7
---
# &lt;vstoRuntime&gt; 요소(Visual Studio에서 Office 개발)
  `vstav3`  네임스페이스의 `vstoRuntime` 요소에는 특정 Office 솔루션에 대해 지원되는 Visual Studio Tools for Office Runtime 버전이 포함됩니다.  
  
## 구문  
  
```  
<vstoRuntime  
    release  
    version  
    supportUrl />  
```  
  
## 요소 및 특성  
 `vstoRuntime` 요소는 필수이며 `vstav3`  네임스페이스에 있습니다. Office 솔루션이 Visual Studio Tools for Office Runtime의 두 가지 버전을 지원하는 경우 응용 프로그램 매니페스트에는 두 개의 `vstoRuntime` 요소가 있습니다.  
  
 `vstoRuntime` 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`release`|필수 요소. Visual Studio Tools for Office Runtime의 릴리스 버전입니다.|  
|`version`|필수 요소. Visual Studio Tools for Office Runtime 버전 번호입니다.|  
|`supportUrl`|선택적 요소. Visual Studio Tools for Office Runtime의 설치 위치에 연결합니다.|  
  
 `vstoRuntime`에는 요소가 없습니다.  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]을 사용하여 배포된 Office 솔루션에 대한 응용 프로그램 매니페스트의 `vstoRuntime` 요소를 보여 줍니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
```  
<vstav3:vstoRuntime release="VSTOR40Beta1" version="10.0.20303" supportUrl="http://www.microsoft.com" />  
```  
  
## 참고 항목  
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)  
  
  