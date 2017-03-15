---
title: "식별자 문 완성 | Microsoft Docs"
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
  - "IntelliSense[JavaScript], 문 완성"
  - "문 완성, JavaScript IntelliSense"
ms.assetid: c2cd4945-c67e-471b-8057-96cfd25f7fb2
caps.latest.revision: 13
caps.handback.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 식별자 문 완성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

JavaScript 명시적 변수 선언에 대 한 입력을 허용 하지 않습니다.  따라서 IntelliSense 항상 완성 목록 개체를 제공할 수 없습니다.  이 다양 한 상황에서 발생할 수 있습니다.  다음은 몇 가지 일반적인 것입니다.  
  
-   매개 변수 선언 되지만 그 다른 곳은 현재 문서에서 다음 예제와 같이 호출 되지 않았습니다.  
  
    ```javascript  
    function illuminate(light) {  
             light.  // Accurate statement completion is not available   
                     // unless illuminate is called elsewhere with a   
                     // parameter that has a value. If it is called only  
                     // in a function that is a sibling to   
                     // illuminate(light) in the call hierarchy, the   
                     // IntelliSense engine also cannot determine the   
                     // parameter type.  
         }  
  
    // Sibling function. No statement completion for light   
    // object in preceding code.  
    function lightLamp() {  
        var x = illuminate(1);  
    }  
  
    // Uncomment the next line to obtain statement completion for  
    // light object in preceding code.  
    // var x = illuminate(1);  
    ```  
  
-   개체 이벤트에 대 한 응답으로 호출 되는 함수입니다.  디자인 타임에 IntelliSense 엔진은이 상황에서 사용 되는 개체의 형식을 확인할 수 없습니다.  
  
     IntelliSense 엔진 이벤트에 일반적으로 사용을 통해 호출 해야 함을 확인할 수 있는 경우 `addEventListener` IntelliSense 정보를 보다 정확 하 게 현재 문서에서에 대 한 이벤트를 제공 합니다.  
  
 IntelliSense 개체를 식별할 수 없는 경우 완성 목록을에 명명 된 항목 또는 현재 문서에 있는 식별자를 IntelliSense 엔진을 채웁니다.  완성 목록에 이러한 식별자 포함 된 경우 정보 아이콘 옆에 나타납니다.  또한 각 식별자에 대 한 도구 설명을 식 알 수 없는 경우를 나타냅니다.  다음 그림과 완성 옵션 개체 형식에 대 한 문을 `light` 는 확인할 수 없습니다 개체와 그 속성은 정의 되지 않습니다 때문에.  그러나의 `intensity` 에 사용 된 되므로 속성 식별자 목록에서 사용할 수 있는 `illuminate` 함수.  
  
 **완료 옵션을 식별할 수 없는 개체에 대 한**  
  
 ![식별자에 대한 JavaScript IntelliSense](../ide/media/js_intellisense_identifiers.png "js\_intellisense\_identifiers")  
  
 XML 문서 주석 또는 JavaScript IntelliSense 확장성 기능을 사용 하 여 완성 목록 개체에 대해 재정의할 수 있습니다.  이러한 기능을 사용 하면 그렇지 않으면 사용할 수 없을 때 IntelliSense의 상세한 정보 및 형식 정보를 제공할 수 있습니다.  자세한 내용은 [JavaScript IntelliSense 확장](../ide/extending-javascript-intellisense.md) 및 [방법: JavaScript XML 문서 주석 만들기](../ide/create-xml-documentation-comments-for-javascript-intellisense.md)을 참조하십시오.  
  
## 참고 항목  
 [JavaScript IntelliSense](../ide/javascript-intellisense.md)