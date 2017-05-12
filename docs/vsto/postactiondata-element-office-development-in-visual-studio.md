---
title: "&lt;postActionData&gt; 요소(Visual Studio에서 Office 개발)"
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
  - "<postActionData> 요소"
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발], <postActionData> 요소"
  - "postActionData 요소"
ms.assetid: e36cbd64-fd27-4413-b293-cf5546fbdfaf
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# &lt;postActionData&gt; 요소(Visual Studio에서 Office 개발)
  `vstav3`  네임스페이스의 `postActionData` 요소는 Office 솔루션이 설치된 후 실행되는 배포 후 작업과 관련된 데이터를 지정합니다.  
  
## 구문  
  
```  
<postActionData>  
</postActionData>  
```  
  
## 요소 및 특성  
 `postActionData` 요소는 선택적이며 `vstav3`  네임스페이스에 있습니다. 하나의 응용 프로그램 매니페스트에서는 각 배포 후 작업에 대해 하나의 `postActionData` 요소만 정의할 수 있습니다.  
  
 `postActions` 요소에는 특성이 없습니다.  
  
 `postActions`에는 자식 요소가 없습니다.  
  
## 배포 후 작업 예제  
  
### 설명  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]을 사용하여 배포된 Office 솔루션에 대한 응용 프로그램 매니페스트의 `postAction` 요소를 보여 줍니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공하는 보다 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<vstav3:postActionData> data in any format </vstav3:postActionData>  
```  
  
## 참고 항목  
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)  
  
  