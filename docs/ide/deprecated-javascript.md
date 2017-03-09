---
title: "&lt;사용되지 않음&gt;(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cf33d371-59da-4310-95ee-d7524fd9d58c
caps.latest.revision: 6
caps.handback.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# &lt;사용되지 않음&gt;(JavaScript)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

사용 되지 않는 함수 또는 메서드를 지정합니다.  
  
## 구문  
  
```  
<deprecated  
    type="deprecate|remove"  
    locid="descriptionID">description  
</deprecated>  
```  
  
#### 매개 변수  
 `type`  
 선택적 요소.  이후 릴리스에서 함수나 메서드의 제거 여부 또는 함수나 메서드가 이미 제거된 후 사용 중 오류가 발생할 수 있는 것을 지정합니다.  추후 버전에서 함수 또는 메서드가 제거되도록 `deprecate` 를 지정할 수 있습니다.  `remove` 가 함수 또는 메서드에 이미 제거된 것을 지정합니다.  
  
 `locid`  
 선택적 요소.  함수나 메서드에 대한 지역화 정보를 위한 식별자입니다.  식별자는 멤버 ID 이거나 OpenAjax 메타 데이터에 의해 정의된 메시지 번들에서 `name` 특성 값에 해당합니다.  식별자 형식은 [\<loc\>](../ide/loc-javascript.md) 요소에서 지정된 형식에 따라 달라집니다.  
  
 `description`  
 선택적 요소.  더 이상 사용되지 않는 메서드나 함수 설명입니다.  
  
## 설명  
 `<deprecated>` 를 포함한 함수에 주석을 다는 데 사용된 요소는 문 앞에 있는 함수 본문에 배치되어야 합니다.  함수를 사용되지 않음으로 표시하면 [\<summary\>](../ide/summary-javascript.md) 요소를 `<deprecated>` 요소로 교체 하는 것이 좋습니다.  
  
## 예제  
 다음 코드는 `<deprecated>` 요소를 사용하는 방법을 보여 줍니다.  
  
```javascript  
function areaFunction(radiusParam) {  
    /// <deprecated type="deprecate" >Determines the area of a circle when supplied a radius parameter.</deprecated>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## 참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)