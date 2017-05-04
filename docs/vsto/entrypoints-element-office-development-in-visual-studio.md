---
title: "&lt;entryPoints&gt; 요소(Visual Studio에서 Office 개발) | Microsoft Docs"
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
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발], <entryPoints> 요소"
ms.assetid: 991d7cbf-85e5-4307-a470-076b2f74d859
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt;entryPoints&gt; 요소(Visual Studio에서 Office 개발)
  `vstav3`  네임스페이스의 `entryPoints` 요소에는 Office 솔루션과 관련된 모든 `entryPoint` 요소가 포함됩니다.  
  
## 구문  
  
```  
<entryPoints>  
    <entryPoint>  
    </entryPoint>  
    <entryPoint>  
    </entryPoint>  
    <entryPoint>  
    </entryPoint>  
</entryPoints>  
```  
  
## 요소 및 특성  
 `entryPoints` 요소는 필수이며 `vstav3`  네임스페이스에 있습니다. 각 Office 솔루션에 대해 응용 프로그램 매니페스트에서 하나의 `entryPoints` 요소가 정의됩니다. 예를 들어 다중 프로젝트 배포에서 세 개의 Office 솔루션을 배포하면 응용 프로그램 매니페스트에 세 개의 `entryPoints` 요소가 있습니다.  
  
 `entryPoints` 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|ID|다중 프로젝트 배포의 경우 필수 요소입니다. Office 솔루션의 이름입니다. Id는 등호\(\=\) 기호를 포함할 수 없습니다.|  
  
 `entryPoints`에는 다음 요소가 있습니다.  
  
### entryPoint  
 필수 요소.`vstav3`  네임스페이스에서 `entryPoint` 요소의 역할은 [&#60;entryPoint&#62; 요소&#40;Visual Studio에서 Office 개발&#41;](../vsto/entrypoint-element-office-development-in-visual-studio.md)에 정의되어 있습니다.  
  
## 문서 수준 사용자 지정 예제  
  
### 설명  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]을 사용하여 배포된 문서 수준 솔루션에 대한 응용 프로그램 매니페스트의 `entryPoints` 요소를 보여 줍니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstav3:entryPoints> <vstav3:entryPoint class="ContosoExcelWorkbook.ThisWorkbook"> <assemblyIdentity name="ContosoExcelWorkbook" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> <vstav3:entryPoint class="ContosoExcelWorkbook.Sheet1"> <assemblyIdentity name="ContosoExcelWorkbook" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> <vstav3:entryPoint class="ContosoExcelWorkbook.Sheet2"> <assemblyIdentity name="ContosoExcelWorkbook" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> <vstav3:entryPoint class="ContosoExcelWorkbook.Sheet3"> <assemblyIdentity name="ContosoExcelWorkbook" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> </vstav3:entryPoints>  
```  
  
## VSTO 추가 기능 예제  
  
### 설명  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]을 사용하여 배포된 응용 프로그램 수준 솔루션에 대한 응용 프로그램 매니페스트의 `entryPoints` 요소를 보여 줍니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstav3:entryPoints> <vstav3:entryPoint class="ContosoOutlookAddIn.ThisAddIn"> <assemblyIdentity name="ContosoOutlookAddIn" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> </vstav3:entryPoints>  
```  
  
## 다중 프로젝트 배포 예제  
  
### 설명  
 다음 코드 예제에서는 다중 프로젝트 배포에 대한 응용 프로그램 매니페스트의 `entryPoints` 요소를 보여 줍니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstav3:entryPoints id="ContosoExcel"> <vstav3:entryPoint class="ContosoExcelWorkbook.ThisWorkbook"> <assemblyIdentity name="ContosoExcelWorkbook" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> <vstav3:entryPoint class="ContosoExcelWorkbook.Sheet1"> <assemblyIdentity name="ContosoExcelWorkbook" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> <vstav3:entryPoint class="ContosoExcelWorkbook.Sheet2"> <assemblyIdentity name="ContosoExcelWorkbook" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> <vstav3:entryPoint class="ContosoExcelWorkbook.Sheet3"> <assemblyIdentity name="ContosoExcelWorkbook" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> </vstav3:entryPoints> <vstav3:entryPoints id="ContosoOutlook"> <vstav3:entryPoint class="ContosoOutlookAddIn.ThisAddIn"> <assemblyIdentity name="ContosoOutlookAddIn" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> </vstav3:entryPoints>  
```  
  
## 참고 항목  
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)  
  
  