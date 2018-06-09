---
title: "JavaScript의 새로운 기능 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 342b68ef-df93-48c4-81de-bdf6b6ce58d9
caps.latest.revision: "33"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 540d10958a7f2d406a6d70a633fc09a2cada8f41
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="what39s-new-in-javascript"></a>JavaScript의 새로운 기능
이 문서에서는 [Edge 모드](http://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx), [!INCLUDE[win8_appname_long](../javascript/includes/win8-appname-long-md.md)] 및 Windows Phone Store 앱에서 모두 지원되는 JavaScript의 새 기능을 나열합니다.  
  
 Edge 모드에서는 지원되지만 [!INCLUDE[win8_appname_long](../javascript/includes/win8-appname-long-md.md)] 앱에서는 더 이상 사용되지 않는 JavaScript 요소를 알아보려면 [버전 정보](../javascript/reference/javascript-version-information.md)를 참조하세요.  
  
> [!IMPORTANT]
>  Visual Studio JavaScript 편집기 및 기타 기능에 대한 정보를 비롯해 JavaScript를 사용하여 [!INCLUDE[win8_appname_long](../javascript/includes/win8-appname-long-md.md)] 및 Windows Phone 스토어 앱을 만드는 방법에 대한 자세한 내용은 [Visual Studio 2013을 사용하여 Windows 스토어 앱 개발](http://go.microsoft.com/fwlink/p/?LinkID=238263)을 참조하세요.  
  
## <a name="new-features-in-javascript"></a>JavaScript의 새로운 기능  
  
|기능|설명|  
|-------------|-----------------|  
|클래스|새로운 구문에서는 [클래스](../javascript/reference/class-statement-javascript.md)의 선언을 지원합니다.|  
|Promise|[Promises](../javascript/reference/promise-object-javascript.md)를 사용하면 더 쉽고 명확한 비동기 코드를 작성할 수 있습니다. Promise 생성자가 `all` 및 `race` 유틸리티 메서드와 함께 지원됩니다.|  
|반복기|이제 반복 가능한 개체(배열, 배열과 유사한 개체, 반복기 등)를 반복하여 고유한 각 속성의 값에 대해 실행될 문이 포함된 사용자 지정 반복 후크를 호출할 수 있습니다. 자세한 내용은 [반복기 및 생성기](../javascript/advanced/iterators-and-generators-javascript.md)를 참조하세요. **참고:**  생성기는 아직 지원되지 않습니다.|  
|화살표 함수|화살표 함수(=>)는 어휘 `this` 바인딩이 포함된 `function` 키워드의 약식 구문입니다.|  
|기본 제공 개체에 대한 새로운 메서드|[Array 개체](../javascript/reference/array-object-javascript.md), [Math 개체](../javascript/reference/math-object-javascript.md), [Number 개체](../javascript/reference/number-object-javascript.md), [Object 개체](../javascript/reference/object-object-javascript.md) 및 [String 개체](../javascript/reference/string-object-javascript.md) 기본 제공 개체에는 데이터 조작 및 검사에 사용할 수 있는 많은 새로운 유틸리티 함수와 속성이 포함되어 있습니다.|  
|개체 리터럴 향상|개체는 이제 계산된 속성, 간결한 메서드 정의 및 같은 이름의 변수로 값이 초기화되는 속성에 대한 약식 구문을 지원합니다. 자세한 내용은 [개체 만들기](../javascript/creating-objects-javascript.md)를 참조하세요.|  
|Proxy|[Proxies](../javascript/reference/proxy-object-javascript.md)를 사용하여 개체에 대한 사용자 지정 동작을 설정할 수 있습니다.|  
|Rest 매개 변수|Rest 매개 변수를 사용하여 함수 호출의 연속된 인수를 배열로 전환할 수 있습니다. 자세한 내용은 [함수](../javascript/functions-javascript.md)를 참조하세요.|  
|스프레드 연산자|[스프레드 연산자](../javascript/reference/spread-operator-decrement-dot-dot-dot-javascript.md)(`...`)는 반복 가능한 식을 개별 인수로 확장합니다. 예를 들어 `a.b(...array)`는 `a.b.apply(a, array)`와 거의 같습니다.|  
|기호|[Symbol](../javascript/reference/symbol-object-javascript.md) 개체를 사용하면 기존 개체 속성을 방해할 가능성, 의도하지 않은 표시 및 다른 코드에 의한 조정되지 않은 추가 없이 속성을 기존 개체에 추가할 수 있습니다.|  
|템플릿 문자열|[템플릿 문자열](../javascript/advanced/template-strings-javascript.md)은 식이 계산되어 문자열 리터럴과 연결될 수 있도록 하는 문자열 리터럴입니다.|  
|유니코드 향상|유니코드 지원 기능이 향상되었습니다. 예를 들어 새로운 이스케이프 시퀀스 형식은 에스트랄 코드 포인트(16진수가 5개 이상인 코드 포인트)를 지원합니다. 자세한 내용은 [특수 문자](../javascript/advanced/special-characters-javascript.md)를 참조하세요.|  
|WeakSet|[WeakSet](../javascript/reference/weakset-object-javascript.md)은 참조되는 위치가 없는 경우 가비지 컬렉션될 개체의 컬렉션입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript 언어 참조](../javascript/javascript-language-reference.md)
