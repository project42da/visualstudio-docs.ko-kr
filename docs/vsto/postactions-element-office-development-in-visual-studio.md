---
title: "&lt;postActions&gt; 요소(Visual Studio에서 Office 개발) | Microsoft Docs"
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
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발], <postActions> 요소"
  - "postActions 요소"
  - "<postActions> 요소"
ms.assetid: 6e487549-fdd6-49bd-be7a-b91f1f964594
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# &lt;postActions&gt; 요소(Visual Studio에서 Office 개발)
  `vstav3`  네임스페이스의 `postActions` 요소에는 배포 후 작업을 설명하는 모든 `postAction` 요소가 포함되며 Office 솔루션 설치 후 실행됩니다.  
  
## 구문  
  
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
  
## 요소 및 특성  
 `postActions` 요소는 선택적이며 `vstav3`  네임스페이스에 있습니다. 하나의 응용 프로그램 매니페스트에서는 하나의 `postActions` 요소만 정의할 수 있습니다.  
  
 `postActions` 요소에는 특성이 없습니다.  
  
 `postActions`에는 다음 요소가 있습니다.  
  
### postAction  
 선택적 요소.`vstav3`  네임스페이스에서 `postAction` 요소의 역할은 [&#60;postAction&#62; 요소&#40;Visual Studio에서 Office 개발&#41;](../vsto/postaction-element-office-development-in-visual-studio.md)에 정의되어 있습니다.  
  
## 배포 후 작업 예제  
  
### 설명  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]을 사용하여 배포된 Office 솔루션에 대한 응용 프로그램 매니페스트의 `postActions` 요소를 보여 줍니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstav3:postActions> <vstav3:postAction> <vstav3:entryPoint class="PostDeploymentAction.PostDeploymentActionSample"> <assemblyIdentity name="PostDeploymentAction" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> <vstav3:postActionData> </vstav3:postActionData> </vstav3:postAction> </vstav3:postActions>  
```  
  
## 참고 항목  
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)  
  
  