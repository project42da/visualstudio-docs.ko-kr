---
title: "&lt;사용자 지정&gt; 요소 (Visual Studio에서 Office 개발) | Microsoft Docs"
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
- <customizations> element
- customizations element
- application manifests [Office development in Visual Studio], <customizations> element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8e84fbba0bf70e28e996dab3c5aa081825447864
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="ltcustomizationsgt-element-office-development-in-visual-studio"></a>&lt;사용자 지정&gt; 요소 (Visual Studio에서 Office 개발)
  `customizations` 네임스페이스의 `vstov4` 요소에는 각 Office 솔루션 설치 및 로드에 대한 모든 정보가 포함됩니다.  
  
## <a name="syntax-for-document-level-customizations"></a>문서 수준 사용자 지정에 대한 구문  
  
```  
<customizations>  
  <customization  
    id  
    <document  
      solutionId  
    />  
  </customization>  
</customizations>  
```  
  
## <a name="syntax-for-vsto-add-ins"></a>VSTO 추가 기능에 대한 구문  
  
```  
<customizations>  
  <customization  
    id  
    <appAddin  
      application  
      loadBehavior  
      keyName>  
    <friendlyName></friendlyName>  
    <description></description>  
    <formRegions></formRegions>  
  </customization>  
</customizations>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `customizations` 요소에는 각 Office 솔루션에 대한 특정 정보가 포함됩니다. 이 요소는 `vstov4=urn:schemas-microsoft-com:vsto.v4`네임스페이스에 있어야 합니다. 어셈블리의 자식 요소도 이 네임스페이스에 있어야 합니다.  
  
 `customizations` 요소에는 특성이 없습니다.  
  
 `customizations` 요소에는 다음 자식 요소가 있습니다.  
  
### <a name="customization"></a>사용자 지정  
 필수. `customization` 요소에는 `vstov4` 네임 스페이스에 정의 된 [&#60; 사용자 지정 &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발 ](../vsto/customization-element-office-development-in-visual-studio.md).  
  
## <a name="example-of-a-document-level-customization"></a>문서 수준 사용자 지정 예제  
  
### <a name="description"></a>설명  
 다음 코드 예제에서는 문서 수준 사용자 지정의 `customizations` 요소를 보여 줍니다.  
  
> [!NOTE]  
>  이 코드 예제는 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### <a name="code"></a>코드  
  
```  
<vstov4:customizations   
  xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
  <vstov4:customization>  
    <vstov4:document   
      solutionId="73e" />  
  </vstov4:customization>  
</vstov4:customizations>  
```  
  
## <a name="example-of-an-vsto-add-in"></a>VSTO 추가 기능의 예제  
  
### <a name="description"></a>설명  
 다음 코드 예제에서는 VSTO 추가 기능의 `customizations` 요소를 보여 줍니다. 양식 영역을 포함하는 Outlook VSTO 추가 기능입니다. 이 코드 예제는 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### <a name="code"></a>코드  
  
```  
<vstov4:customizations   
  xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
  <vstov4:customization>  
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
  </vstov4:customization>  
</vstov4:customizations>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션에 대 한 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)  
  
  