---
title: '&lt;postAction&gt; 요소 (Visual Studio에서 Office 개발)'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <postAction> element
- <postAction> element
- postAction element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: dcab31eea406da695bdedd21b21c0d86cacea220
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693119"
---
# <a name="ltpostactiongt-element-office-development-in-visual-studio"></a>&lt;postAction&gt; 요소 (Visual Studio에서 Office 개발)
  `postAction` 네임스페이스의 `vstav3` 요소에는 `entrypoint` 요소 및 배포 후 작업과 관련된 모든 `postActionData` 요소가 포함되며 Office 솔루션 설치 후 실행됩니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<postAction>  
  <entryPoint>  
  </entryPoint>  
  <postActionData>  
  </postActionData>  
</postAction>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `postAction` 요소는 선택적이며 `vstav3` 네임스페이스에 있습니다. 하나의 응용 프로그램 매니페스트에서는 각 배포 후 작업에 대해 하나의 `postAction` 요소만 정의할 수 있습니다.  
  
 `postAction` 요소에는 특성이 없습니다.  
  
 `postAction` 에는 다음 요소가 있습니다.  
  
### <a name="entrypoint"></a>entrypoint  
 선택 사항입니다. 역할은 `entryPoint` 요소에는 `vstav3` 네임 스페이스에 정의 된 [ &#60;t r y p&#62; 요소 &#40;Visual Studio에서 Office 개발&#41;](../vsto/entrypoints-element-office-development-in-visual-studio.md)합니다.  
  
### <a name="postactiondata"></a>postActionData  
 선택 사항입니다. 역할은 `postActionData` 요소에는 `vstav3` 네임 스페이스에 정의 된 [ &#60;postActionData&#62; 요소 &#40;Visual Studio에서 Office 개발&#41;](../vsto/postactiondata-element-office-development-in-visual-studio.md)합니다.  
  
## <a name="post-deployment-action-example"></a>배포 후 작업 예제  
  
### <a name="description"></a>설명  
 다음 코드 예제에서는 `postAction` 을 사용하여 배포된 Office 솔루션에 대한 응용 프로그램 매니페스트의 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]요소를 보여 줍니다. 이 코드 예제는에 제공 된 큰 예제의 일부 [Office 솔루션에 대 한 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)합니다.  
  
### <a name="code"></a>코드  
  
```xml
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
```  
  
## <a name="see-also"></a>참고자료  
 [Office 솔루션에 대 한 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)  
  
  