---
title: "&lt;appAddin&gt; 요소 (Visual Studio에서 Office 개발) | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <appAddin> element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 27f286f9bde8db68a7190796f1d154a402fb208d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="ltappaddingt-element-office-development-in-visual-studio"></a>&lt;appAddin&gt; 요소 (Visual Studio에서 Office 개발)
  `appAddin` 네임스페이스의 `vstov4` 요소는 VSTO 추가 기능에 대한 사용자 지정 관련 정보를 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<appAddin  
  application  
  loadBehavior  
  keyName>  
  <friendlyName>  
  <description>  
  <formRegions></formRegions>  
</appAddin>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `appAddin` 요소는 필수이며 `vstov4` 네임스페이스에 있습니다. 하나의 응용 프로그램 매니페스트에서는 하나의 `appAddin` 요소만 정의할 수 있습니다.  
  
 `appAddin` 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`application`|필수 요소. Microsoft Office 응용 프로그램을 식별합니다. 값은 Excel, InfoPath, Outlook, PowerPoint, Project, Visio 또는 Word 중 하나입니다.|  
|`loadBehavior`|선택 사항입니다. 기본적으로 이 값이 다음으로 설정되어 `loadBehavior` 가 사용됩니다. 디버깅을 위해서는 이 값을 2로 설정하여 VSTO 추가 기능을 사용하지 않도록 설정할 수 있습니다. 자세한 내용은 [Registry Entries for VSTO Add-ins](../vsto/registry-entries-for-vsto-add-ins.md)에서 LoadBehavior 값 표를 참조하세요.|  
|`keyName`|필수. 이 값은 응용 프로그램에서 VSTO 추가 기능을 로드할 때 사용할 레지스트리 키 이름입니다. 자세한 내용은 [Registry Entries for VSTO Add-ins](../vsto/registry-entries-for-vsto-add-ins.md)을 참조하세요.|  
  
 `appAddin` 요소에는 다음 자식 요소가 있습니다.  
  
### <a name="friendlyname"></a>friendlyName  
 선택 사항입니다. `friendlyName` 요소에 대해서는 설명 [&#60; friendlyName &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발 ](../vsto/friendlyname-element-office-development-in-visual-studio.md).  
  
### <a name="description"></a>설명  
 선택 사항입니다. `description` 요소에 대해서는 설명 [&#60; 설명 &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발 ](../vsto/description-element-office-development-in-visual-studio.md).  
  
### <a name="formregions"></a>formRegions  
 양식 영역을 포함하는 Outlook VSTO 추가 기능에 대해서만 필수 요소. `formRegions` 요소에 대해서는 설명 [&#60; formRegions &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발 ](../vsto/formregions-element-office-development-in-visual-studio.md).  
  
## <a name="vsto-add-in-example"></a>VSTO 추가 기능 예제  
  
### <a name="description"></a>설명  
 다음 코드 예제에서는 `appAddin` 을 사용하여 배포된 Outlook 솔루션의 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]요소를 보여 줍니다. 이 코드 예제는 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### <a name="code"></a>코드  
  
```  
<vstov4:appAddIn   
  application="Outlook"   
  loadBehavior="3"   
  keyName="ContosoOutlookAddIn">  
  <vstov4:friendlyName>  
    ContosoOutlookAddIn  
  </vstov4:friendlyName>  
  <vstov4:description>  
    ContosoOutlookAddIn - Outlook VSTO Add-in   
    created with Visual Studio Tools for Office  
  </vstov4:description>  
  <vstov4:formRegions>  
    <vstov4:formRegion  
        name="OutlookAddIn1.FormRegion1">  
      <vstov4:messageClass name="IPM.Note" />  
      <vstov4:messageClass name="IPM.Contact" />  
      <vstov4:messageClass name="IPM.Appointment" />  
    </vstov4:formRegion>  
  </vstov4:formRegions>  
</vstov4:appAddIn>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션에 대 한 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)  
  
  