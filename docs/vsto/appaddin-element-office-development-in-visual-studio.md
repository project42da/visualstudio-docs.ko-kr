---
title: '&lt;appAddin&gt; 요소 (Visual Studio에서 Office 개발)'
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <appAddin> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0defe437e0778ee9d3c134148a3ca7e4b4cd2ef9
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="ltappaddingt-element-office-development-in-visual-studio"></a>&lt;appAddin&gt; 요소 (Visual Studio에서 Office 개발)
  **appAddin** 의 요소는 `vstov4` 네임 스페이스는 VSTO 추가 기능에 대 한 사용자 지정 관련 정보를 저장 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml 
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
 **appAddin** 요소는 필수 요소 이며는 `vstov4` 네임 스페이스입니다. 하나만 **appAddin** 응용 프로그램 매니페스트에서 정의 된 요소입니다.  
  
 **appAddin** 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|**응용 프로그램**|필수. Microsoft Office 응용 프로그램을 식별합니다. 값은 Excel, InfoPath, Outlook, PowerPoint, Project, Visio 또는 Word 중 하나입니다.|  
|**loadBehavior**|선택 사항입니다. 기본적으로는 **loadBehavior** 이 값 설정 하 여 활성화 합니다. 디버깅을 위해서는 이 값을 2로 설정하여 VSTO 추가 기능을 사용하지 않도록 설정할 수 있습니다. 자세한 내용은에서 LoadBehavior 값 표를 참조 [VSTO 추가 기능에 대 한 레지스트리 항목](../vsto/registry-entries-for-vsto-add-ins.md)합니다.|  
|**키 이름**|필수. 이 값은 응용 프로그램에서 VSTO 추가 기능을 로드할 때 사용할 레지스트리 키 이름입니다. 자세한 내용은 참조 [VSTO 추가 기능에 대 한 레지스트리 항목](../vsto/registry-entries-for-vsto-add-ins.md)합니다.|  
  
 **appAddin** 요소에는 다음 자식 요소가 있습니다.  
  
### <a name="friendlyname"></a>friendlyName  
 선택 사항입니다. **friendlyName** 요소에 대해서는 설명 [ &#60;friendlyName&#62; 요소 &#40;Visual Studio에서 Office 개발&#41;](../vsto/friendlyname-element-office-development-in-visual-studio.md)합니다.  
  
### <a name="description"></a>설명  
 선택 사항입니다. **설명** 요소에 대해서는 설명 [ &#60;설명&#62; 요소 &#40;Visual Studio에서 Office 개발&#41;](../vsto/description-element-office-development-in-visual-studio.md)합니다.  
  
### <a name="formregions"></a>formRegions  
 양식 영역을 포함하는 Outlook VSTO 추가 기능에 대해서만 필수 요소. **formRegions** 요소에 대해서는 설명 [ &#60;formRegions&#62; 요소 &#40;Visual Studio에서 Office 개발&#41;](../vsto/formregions-element-office-development-in-visual-studio.md)합니다.  
  
## <a name="vsto-add-in-example"></a>VSTO 추가 기능 예제  
  
### <a name="description"></a>설명  
 다음 코드 예제에서는 **appAddin** 요소를 사용 하 여 배포 된 Outlook 솔루션의 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]합니다. 이 코드 예제는에 제공 된 큰 예제의 일부 [Office 솔루션에 대 한 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)합니다.  
  
### <a name="code"></a>코드  
  
```xml  
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
  
## <a name="see-also"></a>참고자료  
 [Office 솔루션에 대 한 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)  
  
  