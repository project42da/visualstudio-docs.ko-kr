---
title: "&lt;customErrorReporting&gt; 요소(ClickOnce 배포) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "<customErrorReporting> 요소[ClickOnce 배포 매니페스트]"
ms.assetid: 7d31816e-c692-46b5-9cc9-753284b3bcda
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;customErrorReporting&gt; 요소(ClickOnce 배포)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

오류가 발생할 때 표시할 URI를 지정합니다.  
  
## 구문  
  
```  
<customErrorReporting  
   uri  
/>  
```  
  
## 설명  
 이 요소는 선택적입니다.  이 요소가 없으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서 예외 스택을 보여 주는 오류 대화 상자를 표시합니다.  `customErrorReporting` 요소가 있으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서 `uri` 매개 변수에 지정된 URI를 대신 표시합니다.  대상 URI에는 외부 예외 클래스, 내부 예외 클래스 및 내부 예외 메시지가 매개 변수로 포함됩니다.  
  
 이 요소를 사용하여 응용 프로그램에 오류 보고 기능을 추가합니다.  생성된 URI에는 오류 형식에 대한 정보가 포함되므로 웹 사이트에서 해당 정보를 구문 분석하여 적절한 문제 해결 화면을 표시할 수 있습니다.  
  
## 예제  
 다음 코드 조각에서는 `customErrorReporting` 요소와 생성된 URI를 함께 보여 줍니다.  
  
```  
<customErrorReporting uri=http://www.contoso.com/applications/error.asp />  
  
Example Generated Error:  
http://www.contoso.com/applications/error.asp? outer=System.Deployment.Application.InvalidDeploymentException&&inner=System.Deployment.Application.InvalidDeploymentException&&msg=The%20application%20manifest%20is%20signed,%20but%20the%20deployment%20manifest%20is%20unsigned.%20Both%20manifests%20must%20be%20either%20signed%20or%20unsigned.  
```  
  
## 참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)