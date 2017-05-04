---
title: "&lt;customHostSpecified&gt; 요소(Visual Studio에서 Office 개발) | Microsoft Docs"
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
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발], <customHostSpecified> 요소"
  - "<customHostSpecified> 요소"
  - "customHostSpecified 요소"
ms.assetid: 2212b7eb-bf94-4398-b9ea-0ab00203203b
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 22
---
# &lt;customHostSpecified&gt; 요소(Visual Studio에서 Office 개발)
  `customHostSpecified` 요소는 이 솔루션이 독립 실행형 응용 프로그램이 아님을 나타냅니다.  Office 솔루션에는 Microsoft Office 응용 프로그램 내에서 호스팅되는 구성 요소가 들어 있습니다.  
  
## 구문  
  
```  
<customHostSpecified />  
```  
  
## 요소 및 특성  
 `customHostSpecified` 요소는 Office 솔루션의 필수 요소입니다.  이 요소는 `co.v1` 네임스페이스에 포함되어 있으며, 이 배포에 사용자 지정 호스트 내부에 배포되고 독립 실행형 응용 프로그램이 아닌 구성 요소가 포함되어 있음을 지정합니다.  
  
 이 요소는 응용 프로그램 매니페스트에 있는 첫 번째 `<entrypoint>` 요소의 자식입니다.  설치 중 `<entrypoint>` 요소나 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]에서 유효성 검사 오류를 발생시키는 다른 자식 요소는 있을 수 없습니다.  
  
 이 요소에는 특성과 자식 요소가 없습니다.  
  
## 예제  
 다음코딩하다예제는 `customHostSpecified` 요소에는응용 프로그램매니페스트는 Office솔루션에 대 한.   이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)에서 제공되는 보다 큰 예제의 일부입니다.  
  
```  
<entryPoint>  
    <co.v1:customHostSpecified />  
</entryPoint>  
```  
  
## 참고 항목  
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)  
  
  