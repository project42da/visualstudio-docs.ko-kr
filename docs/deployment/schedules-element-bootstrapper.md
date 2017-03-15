---
title: "&lt;Schedules&gt; 요소(부트스트래퍼) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "<Schedules> 요소[부트스트래퍼]"
ms.assetid: 28d094cf-64f5-42b1-bd8a-3697082aab4f
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 5
---
# &lt;Schedules&gt; 요소(부트스트래퍼)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`Schedules` 요소에는 `Command` 요소로 정의한 명령을 실행할 특정 시간을 정의하는 `Schedule` 요소가 들어 있습니다.  
  
## 구문  
  
```  
<Schedules>  
    <Schedule  
        Name  
    >  
        <BuildList />  
        <BeforePackage />  
        <AfterPackage />  
    </Schedule>  
</Schedules>  
```  
  
## 요소 및 특성  
 `Schedules` 요소는 `Product` 요소의 자식입니다.  각 `Product` 요소에는 `Schedules` 요소가 하나만 있을 수 있습니다.  `Schedules` 요소에는 특성이 없습니다.  
  
## Schedule  
 `Schedule` 요소는 `Schedules` 요소의 자식입니다.  `Schedules` 요소에는 `Schedule` 요소가 적어도 한 개 있어야 합니다.  
  
 `Schedule`에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Name`|필수 요소.  일정 항목의 이름입니다.  이 이름은 `Command` 요소의 `ScheduleName` 속성에 해당합니다.  `Command`에서 명명된 일정을 참조하는 경우 이 `Schedule` 요소에서 지정한 시간에만 명령이 실행됩니다.  일정은 `FailIf` 및 `BypassIf` 요소와 연결될 수도 있습니다. 이렇게 하면 지정한 일정에만 이러한 조건 테스트를 실행하도록 제한됩니다.  자세한 내용은 [\<Commands\> 요소](../deployment/commands-element-bootstrapper.md)를 참조하십시오.|  
  
 지정된 `Schedule` 요소에는 다음과 같은 자식이 하나만 있을 수 있습니다.  
  
## BuildList  
 `BuildList` 요소는 부트스트래핑 응용 프로그램이 시작된 직후에 명령을 실행하도록 설치 관리자에 지시합니다.  
  
## BeforePackage  
 `BeforePackage` 요소는 지정된 패키지를 설치하기 전에 명령을 실행하도록 설치 관리자에 지시합니다.  
  
## AfterPackage  
 `AfterPackage` 요소는 지정된 패키지를 설치한 후에 명령을 실행하도록 설치 관리자에 지시합니다.  
  
## 참고 항목  
 [\<Product\> 요소](../deployment/product-element-bootstrapper.md)   
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)