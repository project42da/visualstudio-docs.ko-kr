---
title: "&lt;문서&gt; 요소 (Visual Studio에서 Office 개발) | Microsoft Docs"
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
- document element
- application manifests [Office development in Visual Studio], <document> element
- <document> element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 38b03c2a4980891d9a6841b24365db32ee555de4
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="ltdocumentgt-element-office-development-in-visual-studio"></a>&lt;문서&gt; 요소 (Visual Studio에서 Office 개발)
  `document` 의 요소는 `vstov4` 네임 스페이스는 문서 수준 사용자 지정에 대 한 사용자 지정 관련 정보를 저장 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<document solutionId />  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 문서 수준 사용자 지정에만 필요합니다. `document` 요소는는 `vstov4` 네임 스페이스입니다. `document` 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`solutionId`|필수. 고유 하 게 식별 하는 문서 수준 솔루션에서 Visual Studio Tools for Office 런타임에서 사용 하는 GUID입니다. 이 값은 _AssemblyLocation 사용자 지정 문서 속성으로 저장 됩니다. 자세한 내용은 [Custom Document Properties Overview](../vsto/custom-document-properties-overview.md)을 참조하세요.|  
  
 `document`자식 요소가 없습니다.  
  
## <a name="document-level-customization-example"></a>문서 수준 사용자 지정 예제  
  
### <a name="description"></a>설명  
 다음 코드 예제는 `document` 요소를 사용 하 여 배포 되는 문서 수준 Office 솔루션에 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]합니다. 이 코드 예제는 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### <a name="code"></a>코드  
  
```  
<vstov4:document   
  solutionId="73e" />  
```  
  
## <a name="see-also"></a>참고 항목  
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션에 대 한 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)  
  
  