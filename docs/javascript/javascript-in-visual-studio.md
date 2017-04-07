---
title: "Visual Studio의 JavaScript | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f3eee13e-30e4-4bc1-81f5-058d7e379b75
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 77e7ce26df70e41e2328442454fe78c7a663f1f3
ms.openlocfilehash: de00ef86413571739446b61427c3a8e6c4680c06
ms.lasthandoff: 03/08/2017

---
# <a name="javascript-in-visual-studio"></a>Visual Studio의 JavaScript
JavaScript는 Visual Studio의 고급 언어입니다. Visual Studio IDE에서 JavaScript 코드를 작성할 때 대부분 또는 모든 표준 편집 지원(코드 조각, IntelliSense 등)을 사용할 수 있습니다. 여러 응용 프로그램 형식 및 서비스에 대해 JavaScript 코드를 작성할 수 있습니다.  
  
 JavaScript 언어 참조 문서에 대한 자세한 내용은 [JavaScript](https://docs.microsoft.com/scripting/javascript/javascript-language-reference)를 참조하세요.
  
 특정 버전의 Visual Studio나 특정 Visual Studio 확장은 HTML 및 JavaScript를 사용하여 특정 응용 프로그램 유형 및 서비스를 개발하는 데 필요할 수 있습니다. 다음 목록에 자세한 내용을 볼 수 있는 링크가 있습니다.  
  
-   Apache Cordova를 사용하여 플랫폼 간 앱을 만들려면 [Apache Cordova용 Visual Studio Tools](https://docs.microsoft.com/visualstudio/cross-platform/tools-for-cordova/)를 참조하세요.  
  
-   Visual Studio에서 사용할 수 있는 JavaScript 기술에 대한 링크는 [JavaScript](https://docs.microsoft.com/scripting/javascript/) 및 [스크립팅 기술](https://docs.microsoft.com/scripting/) 페이지를 참조하세요.
  
 Visual Studio의 JavaScript 편집기는 IntelliSense를 지원합니다. 자세한 내용은 [JavaScript IntelliSense](../ide/javascript-intellisense.md)를 참조하세요.  
  
## <a name="whats-new-in-javascript"></a>JavaScript의 새로운 기능  
 JavaScript의 새로운 기능은 다음 표에 나와 있습니다.  
  
|기능|설명|  
|-------------|-----------------|  
|클래스|새로운 구문에서는 [클래스](http://msdn.microsoft.com/Library/bf45ebad-4678-4062-88df-55d32b603c69)의 선언을 지원합니다.|  
|Promise|[Promises](http://msdn.microsoft.com/Library/358ad98b-f7fa-448c-9ee0-ef1e2a45e9c6)를 사용하면 더 쉽고 명확한 비동기 코드를 작성할 수 있습니다. Promise 생성자가 `all` 및 `race` 유틸리티 메서드와 함께 지원됩니다.|  
|반복기|이제 반복 가능한 개체(배열, 배열과 유사한 개체, 반복기 등)를 반복하여 고유한 각 속성의 값에 대해 실행될 문이 포함된 사용자 지정 반복 후크를 호출할 수 있습니다. 자세한 내용은 [반복기 및 생성기](http://msdn.microsoft.com/Library/68ef5b2f-0349-492b-b557-73ff2a2f90cf)를 참조하세요. **참고:**  생성기는 아직 지원되지 않습니다.|  
|화살표 함수|화살표 함수(=>)는 어휘 `this` 바인딩이 포함된 `function` 키워드의 약식 구문입니다.|  
|기본 제공 개체에 대한 새로운 메서드|[Array 개체](http://msdn.microsoft.com/Library/08e5f552-0797-4b48-8164-609582fc18c9), [Math 개체](http://msdn.microsoft.com/Library/607b94cb-921c-43cd-b514-fdbc13aeced6), [Number 개체](http://msdn.microsoft.com/Library/76e87c37-cf6c-46cc-bafa-04be1fe3d78d), [Object 개체](http://msdn.microsoft.com/Library/d24ef8fc-217b-4828-94e1-19f72780bae0) 및 [String 개체](http://msdn.microsoft.com/Library/8063ecd5-5778-4e87-b985-b21420171914) 기본 제공 개체에는 데이터 조작 및 검사에 사용할 수 있는 많은 새로운 유틸리티 함수와 속성이 포함되어 있습니다.|  
|개체 리터럴 향상|개체는 이제 계산된 속성, 간결한 메서드 정의 및 같은 이름의 변수로 값이 초기화되는 속성에 대한 약식 구문을 지원합니다. 자세한 내용은 [개체 만들기](http://msdn.microsoft.com/Library/58d1baa5-4fe8-4a56-a926-5b11765df704)를 참조하세요.|  
|Proxy|[Proxies](http://msdn.microsoft.com/Library/2b89abee-04fa-47e6-9676-980016cff5f8)를 사용하여 개체에 대한 사용자 지정 동작을 설정할 수 있습니다.|  
|Rest 매개 변수|Rest 매개 변수를 사용하여 함수 호출의 연속된 인수를 배열로 전환할 수 있습니다. 자세한 내용은 [함수](http://msdn.microsoft.com/Library/e2a72b5a-3edd-43d8-95e8-91721b38c1c1)를 참조하세요.|  
|스프레드 연산자|[스프레드 연산자](http://msdn.microsoft.com/Library/10263a4c-bd27-4d87-9917-fb4b6bf373db)(`…`)는 반복 가능한 식을 개별 인수로 확장합니다. 예를 들어 `a.b(…array)`는 `a.b.apply(a, array)`와 거의 같습니다.|  
|기호|[Symbol](http://msdn.microsoft.com/Library/2ad059f1-4b7f-4758-882a-c74ce1283ab0) 개체를 사용하면 기존 개체 속성을 방해할 가능성, 의도하지 않은 표시 및 다른 코드에 의한 조정되지 않은 추가 없이 속성을 기존 개체에 추가할 수 있습니다.|  
|템플릿 문자열|[템플릿 문자열](http://msdn.microsoft.com/Library/f2e525a5-b0fc-49c3-95a0-641788e5c12a)은 식이 계산되어 문자열 리터럴과 연결될 수 있도록 하는 문자열 리터럴입니다.|  
|유니코드 향상|유니코드 지원 기능이 향상되었습니다. 예를 들어 새로운 이스케이프 시퀀스 형식은 에스트랄 코드 포인트(16진수가&5;개 이상인 코드 포인트)를 지원합니다. 자세한 내용은 [특수 문자](http://msdn.microsoft.com/Library/3b38b1bd-1f0f-4748-b13e-55cab36fd126)를 참조하세요.|  
|WeakSet|[WeakSet](http://msdn.microsoft.com/Library/f97e6e7c-d678-4e32-978e-d949a7cafa3a)은 참조되는 위치가 없는 경우 가비지 컬렉션될 개체의 컬렉션입니다.|
