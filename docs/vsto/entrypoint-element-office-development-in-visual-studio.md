---
title: "&lt;entryPoint&gt; 요소 (Visual Studio에서 Office 개발) | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <entryPoint> element
- <entryPoint> element
- entryPoint element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 2416a50707d36295a6ddb1c2388f6ee9ef37b113
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="ltentrypointgt-element-office-development-in-visual-studio"></a>&lt;entryPoint&gt; 요소 (Visual Studio에서 Office 개발)
  `entryPoint` 네임스페이스의 각 `vstav3` 요소는 이 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 응용 프로그램이 설치될 때 실행되어야 하는 사용자 지정 어셈블리를 식별합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<entryPoint class>  
    <assemblyIdentity />  
</entryPoint>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `entryPoint` 요소는 필수이며 `vstav3` 네임스페이스에 있습니다.  
  
 각 `entryPoint` 요소에는 하나의 사용자 지정 어셈블리만 포함할 수 있습니다. 응용 프로그램 매니페스트에 여러 `entryPoint` 요소가 정의될 수 있습니다.  
  
 `entryPoint` 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`class`|필수. 실행할 사용자 지정 어셈블리를 식별합니다. 이 특성의 구문은 *NamespaceName.ClassName*입니다.|  
  
 `entryPoint` 에는 다음 요소가 있습니다.  
  
### <a name="assemblyidentity"></a>assemblyIdentity  
 필수. `assemblyIdentity` 네임스페이스의 `vstav3` 요소는 `assemblyIdentity` 응용 프로그램 매니페스트의 기존 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 요소를 참조합니다.  
  
 역할 `assemblyIdentity` 및 해당 특성에 정의 되었는지 [&#60; assemblyIdentity &#62; 요소 &#40; ClickOnce 응용 프로그램 &#41; ](/visualstudio/deployment/assemblyidentity-element-clickonce-application).  
  
## <a name="document-level-customization-example"></a>문서 수준 사용자 지정 예제  
  
### <a name="description"></a>설명  
 다음 코드 예제에서는 `entryPoint` 을 사용하여 배포된 문서 수준의 Office 솔루션에 대한 응용 프로그램 매니페스트의 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]요소를 보여 줍니다. 이 코드 예제는 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### <a name="code"></a>코드  
  
```  
<vstav3:entryPoint   
  class="ContosoExcelWorkbook.ThisWorkbook">  
  <assemblyIdentity   
    name="ContosoExcelWorkbook"   
    version="1.0.0.0"   
    language="neutral"   
    processorArchitecture="msil" />  
</vstav3:entryPoint>  
<vstav3:entryPoint   
  class="ContosoExcelWorkbook.Sheet1">  
  <assemblyIdentity   
    name="ContosoExcelWorkbook"   
    version="1.0.0.0"   
    language="neutral"   
    processorArchitecture="msil" />  
</vstav3:entryPoint>  
<vstav3:entryPoint   
  class="ContosoExcelWorkbook.Sheet2">  
  <assemblyIdentity   
    name="ContosoExcelWorkbook"   
    version="1.0.0.0"   
    language="neutral"   
    processorArchitecture="msil" />  
</vstav3:entryPoint>  
<vstav3:entryPoint   
  class="ContosoExcelWorkbook.Sheet3">  
  <assemblyIdentity   
    name="ContosoExcelWorkbook"   
    version="1.0.0.0"   
    language="neutral"   
    processorArchitecture="msil" />  
</vstav3:entryPoint>  
```  
  
## <a name="vsto-add-in-example"></a>VSTO 추가 기능 예제  
  
### <a name="description"></a>설명  
 다음 코드 예제에서는 `entryPoint` 을 사용하여 배포된 응용 프로그램 수준의 Office 솔루션에 대한 응용 프로그램 매니페스트의 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]요소를 보여 줍니다. 이 코드 예제는 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### <a name="code"></a>코드  
  
```  
<vstav3:entryPoint   
  class="ContosoOutlookAddIn.ThisAddIn">  
  <assemblyIdentity   
    name="ContosoOutlookAddIn"   
    version="1.0.0.0"   
    language="neutral"   
    processorArchitecture="msil" />  
</vstav3:entryPoint>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션에 대 한 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)  
  
  