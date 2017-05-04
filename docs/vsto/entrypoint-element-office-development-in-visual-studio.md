---
title: "&lt;entryPoint&gt; 요소(Visual Studio에서 Office 개발) | Microsoft Docs"
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
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발],<entryPoint> 요소"
  - "<entryPoint> 요소"
  - "entryPoint 요소"
ms.assetid: 0c9d22d0-0852-4260-89c6-b83f24e48793
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 22
---
# &lt;entryPoint&gt; 요소(Visual Studio에서 Office 개발)
  `vstav3`  네임스페이스의 각 `entryPoint` 요소는 이 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 응용 프로그램이 설치될 때 실행되어야 하는 사용자 지정 어셈블리를 식별합니다.  
  
## 구문  
  
```  
<entryPoint class>  
    <assemblyIdentity />  
</entryPoint>  
```  
  
## 요소 및 특성  
 `entryPoint` 요소는 필수이며 `vstav3`  네임스페이스에 있습니다.  
  
 각 `entryPoint` 요소에는 하나의 사용자 지정 어셈블리만 포함할 수 있습니다. 응용 프로그램 매니페스트에 여러 `entryPoint` 요소가 정의될 수 있습니다.  
  
 `entryPoint` 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`class`|필수 요소. 실행할 사용자 지정 어셈블리를 식별합니다. 이 특성의 구문은 *NamespaceName.ClassName*입니다.|  
  
 `entryPoint`에는 다음 요소가 있습니다.  
  
### assemblyIdentity  
 필수 요소.`vstav3`  네임스페이스의 `assemblyIdentity` 요소는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 응용 프로그램 매니페스트의 기존 `assemblyIdentity` 요소를 참조합니다.  
  
 `assemblyIdentity`의 역할 및 해당 특성은 [&#60;assemblyIdentity&#62; 요소&#40;ClickOnce 응용 프로그램&#41;](~/deployment/assemblyidentity-element-clickonce-application.md)에 정의되어 있습니다.  
  
## 문서 수준 사용자 지정 예제  
  
### 설명  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]을 사용하여 배포된 문서 수준의 Office 솔루션에 대한 응용 프로그램 매니페스트의 `entryPoint` 요소를 보여 줍니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstav3:entryPoint class="ContosoExcelWorkbook.ThisWorkbook"> <assemblyIdentity name="ContosoExcelWorkbook" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> <vstav3:entryPoint class="ContosoExcelWorkbook.Sheet1"> <assemblyIdentity name="ContosoExcelWorkbook" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> <vstav3:entryPoint class="ContosoExcelWorkbook.Sheet2"> <assemblyIdentity name="ContosoExcelWorkbook" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> <vstav3:entryPoint class="ContosoExcelWorkbook.Sheet3"> <assemblyIdentity name="ContosoExcelWorkbook" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint>  
```  
  
## VSTO 추가 기능 예제  
  
### 설명  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]을 사용하여 배포된 응용 프로그램 수준의 Office 솔루션에 대한 응용 프로그램 매니페스트의 `entryPoint` 요소를 보여 줍니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstav3:entryPoint class="ContosoOutlookAddIn.ThisAddIn"> <assemblyIdentity name="ContosoOutlookAddIn" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint>  
```  
  
## 참고 항목  
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)  
  
  