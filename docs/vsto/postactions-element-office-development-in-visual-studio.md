---
title: '&lt;postActions&gt; 요소 (Visual Studio에서 Office 개발) | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <postActions> element
- postActions element
- <postActions> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2c4dafa1c5ac7ef296ba388ecdfd93d00afef708
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ltpostactionsgt-element-office-development-in-visual-studio"></a>&lt;postActions&gt; 요소 (Visual Studio에서 Office 개발)
  `postActions` 네임스페이스의 `vstav3` 요소에는 배포 후 작업을 설명하는 모든 `postAction` 요소가 포함되며 Office 솔루션 설치 후 실행됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
<postActions>  
  <postAction>  
    <entryPoint>  
    </entryPoint>  
    <postActionData>  
    </postActionData>  
  </postAction>  
</postActions>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `postActions` 요소는 선택적이며 `vstav3` 네임스페이스에 있습니다. 하나의 응용 프로그램 매니페스트에서는 하나의 `postActions` 요소만 정의할 수 있습니다.  
  
 `postActions` 요소에는 특성이 없습니다.  
  
 `postActions` 에는 다음 요소가 있습니다.  
  
### <a name="postaction"></a>postAction  
 선택 사항입니다. 역할은 `postAction` 요소에는 `vstav3` 네임 스페이스에 정의 된 [ &#60;postAction&#62; 요소 &#40;Visual Studio에서 Office 개발&#41;](../vsto/postaction-element-office-development-in-visual-studio.md)합니다.  
  
## <a name="post-deployment-action-example"></a>배포 후 작업 예제  
  
### <a name="description"></a>설명  
 다음 코드 예제에서는 `postActions` 을 사용하여 배포된 Office 솔루션에 대한 응용 프로그램 매니페스트의 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]요소를 보여 줍니다. 이 코드 예제는 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### <a name="code"></a>코드  
  
```  
<vstav3:postActions>  
  <vstav3:postAction>  
    <vstav3:entryPoint   
      class="PostDeploymentAction.PostDeploymentActionSample">  
      <assemblyIdentity   
        name="PostDeploymentAction"   
        version="1.0.0.0"   
        language="neutral"   
        processorArchitecture="msil" />  
    </vstav3:entryPoint>  
    <vstav3:postActionData>  
    </vstav3:postActionData>  
  </vstav3:postAction>  
</vstav3:postActions>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션에 대 한 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)  
  
  