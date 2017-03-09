---
title: "&lt;summary&gt;(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "summary JavaScript XML 태그"
  - "<summary> JavaScript XML 태그"
ms.assetid: 6540582d-bdb3-42ec-ad2f-c176783e6f9c
caps.latest.revision: 11
caps.handback.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# &lt;summary&gt;(JavaScript)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

메서드 또는 함수에 대한 설명을 지정합니다.  
  
## 구문  
  
```  
<summary locid="descriptionID">description  
</summary>  
```  
  
#### 매개 변수  
 `locid`  
 선택적 요소.  함수나 메서드에 대한 지역화 정보를 위한 식별자입니다.  식별자는 멤버 ID 이거나 OpenAjax 메타 데이터에 의해 정의된 메시지 번들에서 `name` 특성 값에 해당합니다.  식별자 형식은 [\<loc\>](../ide/loc-javascript.md) 요소에서 지정된 형식에 따라 달라집니다.  
  
 `description`  
 선택적 요소.  함수 또는 메서드 설명입니다.  
  
## 설명  
 [\<summary\>](../ide/summary-javascript.md), [\<param\>](../ide/param-javascript.md), 및 [\<returns\>](../ide/returns-javascript.md) 를 포함한 함수에 주석을 다는 데 사용된 요소는 문 앞에 있는 함수 본문에 배치 되어야 합니다.  
  
## 예제  
 다음 코드는 `<summary>` 요소를 사용하는 방법을 보여 줍니다.  
  
```javascript  
function areaFunction(radiusParam)  
{  
    /// <summary>Determines the area of a circle when supplied a radius parameter.</summary>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## 참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)