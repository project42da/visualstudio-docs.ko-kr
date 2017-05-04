---
title: "&lt;postAction&gt; 요소(Visual Studio에서 Office 개발) | Microsoft Docs"
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
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발], <postAction> 요소"
  - "<postAction> 요소"
  - "postAction 요소"
ms.assetid: a047e2e2-9732-4140-b8bd-bc5bd1b84291
caps.latest.revision: 14
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# &lt;postAction&gt; 요소(Visual Studio에서 Office 개발)
  `vstav3`  네임스페이스의 `postAction` 요소에는 `entrypoint` 요소 및 배포 후 작업과 관련된 모든 `postActionData` 요소가 포함되며 Office 솔루션 설치 후 실행됩니다.  
  
## 구문  
  
```  
<postAction>  
  <entryPoint>  
  </entryPoint>  
  <postActionData>  
  </postActionData>  
</postAction>  
```  
  
## 요소 및 특성  
 `postAction` 요소는 선택적이며 `vstav3`  네임스페이스에 있습니다. 하나의 응용 프로그램 매니페스트에서는 각 배포 후 작업에 대해 하나의 `postAction` 요소만 정의할 수 있습니다.  
  
 `postAction` 요소에는 특성이 없습니다.  
  
 `postAction`에는 다음 요소가 있습니다.  
  
### entryPoint  
 선택적 요소.`vstav3`  네임스페이스에서 `entryPoint` 요소의 역할은 [&#60;entryPoints&#62; 요소&#40;Visual Studio에서 Office 개발&#41;](../vsto/entrypoints-element-office-development-in-visual-studio.md)에 정의되어 있습니다.  
  
### postActionData  
 선택적 요소.`vstav3`  네임스페이스에서 `postActionData` 요소의 역할은 [&#60;postActionData&#62; 요소&#40;Visual Studio에서 Office 개발&#41;](../vsto/postactiondata-element-office-development-in-visual-studio.md)에 정의되어 있습니다.  
  
## 배포 후 작업 예제  
  
### 설명  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]을 사용하여 배포된 Office 솔루션에 대한 응용 프로그램 매니페스트의 `postAction` 요소를 보여 줍니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstav3:postAction> <vstav3:entryPoint class="PostDeploymentAction.PostDeploymentActionSample"> <assemblyIdentity name="PostDeploymentAction" version="1.0.0.0" language="neutral" processorArchitecture="msil" /> </vstav3:entryPoint> <vstav3:postActionData> </vstav3:postActionData> </vstav3:postAction>  
```  
  
## 참고 항목  
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)  
  
  