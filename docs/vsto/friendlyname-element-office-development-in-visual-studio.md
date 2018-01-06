---
title: "&lt;friendlyName&gt; 요소 (Visual Studio에서 Office 개발) | Microsoft Docs"
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
helpviewer_keywords: application manifests [Office development in Visual Studio], <friendlyName> element
ms.assetid: 80250fbf-fccf-4baa-948e-ace7f4449e9c
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9b08121ffb9a9320f7a0d8a8828ee166f94bfa0a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltfriendlynamegt-element-office-development-in-visual-studio"></a>&lt;friendlyName&gt; 요소 (Visual Studio에서 Office 개발)
  `friendlyName` 네임스페이스의 `vstov4` 요소는 설치된 프로그램 목록에 표시되는 이름을 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<friendlyName>  
</friendlyName>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `friendlyName` 요소는 `vstov4` 네임스페이스에 있습니다. 값이 컴퓨터에 설치된 프로그램 목록 및 Microsoft Office 응용 프로그램의 COM VSTO 추가 기능 대화 상자에 표시됩니다.  
  
 `friendlyName` 요소에는 특성 또는 자식 요소가 없습니다.  
  
## <a name="vsto-add-in-example"></a>VSTO 추가 기능 예제  
  
### <a name="description"></a>설명  
 다음 코드 예제에서는 `friendlyName` 을 사용하여 배포된 응용 프로그램 수준 솔루션의 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]요소를 보여 줍니다. 이 코드 예제는 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### <a name="code"></a>코드  
  
```  
<vstov4:friendlyName>  
  ContosoOutlookAddIn  
</vstov4:friendlyName>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션에 대 한 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)  
  
  