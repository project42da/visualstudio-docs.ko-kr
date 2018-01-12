---
title: "&lt;설명&gt; 요소 (Visual Studio에서 Office 개발) | Microsoft Docs"
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
- description element
- <description> element
- application manifests [Office development in Visual Studio], <description> element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: a2fdb8fb394ce2ccb7bb549df55ef1649b68d5cb
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="ltdescriptiongt-element-office-development-in-visual-studio"></a>&lt;설명&gt; 요소 (Visual Studio에서 Office 개발)
  `description` 네임스페이스의 `vstov4` 요소는 Microsoft Office 응용 프로그램의 COM 추가 기능 대화 상자에 나타나는 Office 솔루션에 대한 설명을 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<description>  
</description>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 선택 사항입니다. `description` 요소는 `vstov4` 네임스페이스에 있습니다. Microsoft Office 응용 프로그램의 COM 추가 기능 대화 상자에 표시되는 추가 기능에 대한 설명이 포함됩니다.  
  
 `description` 요소에는 특성 또는 요소가 없습니다.  
  
## <a name="vsto-add-in-example"></a>VSTO 추가 기능 예제  
  
### <a name="description"></a>vstov4  
 다음 코드 예제에서는 `description` 를 사용하여 배포된 응용 프로그램 수준 솔루션의 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]요소를 보여 줍니다. 이 코드 예제는 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### <a name="code"></a>코드  
  
```  
<vstov4:description>  
  ContosoOutlookAddIn - Outlook add-in   
  created with Visual Studio Tools for Office  
</vstov4:description>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션에 대 한 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)  
  
  