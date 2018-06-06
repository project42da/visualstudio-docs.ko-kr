---
title: '&lt;일정&gt; 요소 (부트스트래퍼) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <Schedules> element [bootstrapper]
ms.assetid: 28d094cf-64f5-42b1-bd8a-3697082aab4f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9c551bc9335dc41f82800e2c3435d8508967a6db
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815472"
---
# <a name="ltschedulesgt-element-bootstrapper"></a>&lt;일정&gt; 요소 (부트스트래퍼)
`Schedules` 요소에 포함 되어 `Schedule` 특정 시간에 의해 정의 되는 명령 정의 하는 요소는 `Command` 요소를 실행 해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml
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
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `Schedules` 의 자식인 요소는 `Product` 요소입니다. 각 `Product` 요소는 하나만 있을 수 있습니다 `Schedules` 요소입니다. `Schedules` 요소에는 특성이 없습니다.  
  
## <a name="schedule"></a>일정  
 `Schedule` 의 자식인 요소는 `Schedules` 요소입니다. A `Schedules` 요소가 하나 이상 있어야 `Schedule` 요소입니다.  
  
 `Schedule` 에 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Name`|필수. 일정 항목의 이름입니다. 이에 해당는 `ScheduleName` 의 속성은 `Command` 요소입니다. 경우는 `Command` 명명 된 일정을 참조 하 여 지정 된 시간에 실행만 됩니다 `Schedule` 요소입니다. 일정와 연결 될 수도 `FailIf` 및 `BypassIf` 지정 된 일정에서 실행에 이러한 조건부 검사를 제한 하는 요소입니다. 자세한 내용은 참조 [ \<명령 > 요소](../deployment/commands-element-bootstrapper.md)합니다.|  
  
 지정 된 `Schedule` 요소는 다음과 같은 자식이 하나만 있을 수 있습니다.  
  
## <a name="buildlist"></a>BuildList  
 `BuildList` 요소 부트스트래핑 응용 프로그램이 시작 된 후에 즉시 명령을 실행 하는 설치 관리자에 게 지시 합니다.  
  
## <a name="beforepackage"></a>BeforePackage  
 `BeforePackage` 요소는 지정 된 패키지를 설치 하기 전에 명령을 실행 하는 설치 관리자에 게 지시 합니다.  
  
## <a name="afterpackage"></a>AfterPackage  
 `AfterPackage` 요소는 지정 된 패키지를 설치한 후 명령을 실행 하는 설치 관리자에 게 지시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<제품 > 요소](../deployment/product-element-bootstrapper.md)   
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)