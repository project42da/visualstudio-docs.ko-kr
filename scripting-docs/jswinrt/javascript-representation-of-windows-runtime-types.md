---
title: "Windows 런타임 형식의 JavaScript 표현 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Runtime types [JavaScript]
- JavaScript, Windows Runtime types
ms.assetid: f4851802-8b40-4afa-ba6c-8a162a9a43cc
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: 8e4c21675d26bf857391d92b99b4a94637a761ca
ms.contentlocale: ko-kr
ms.lasthandoff: 08/11/2017

---
# <a name="javascript-representation-of-windows-runtime-types"></a>Windows 런타임 형식의 JavaScript 표현
다음 표에서는 JavaScript에서 Windows 런타임 형식을 표시하는 방법을 설명합니다.  
  
> [!IMPORTANT]
>  Windows 런타임 기능은 Internet Explorer에서 실행되는 앱에는 사용할 수 없습니다.  
  
## <a name="windows-runtime-types-in-javascript"></a>JavaScript의 Windows 런타임 형식  
  
|Windows 런타임 형식|JavaScript 표현|설명|  
|--------------------------|-------------------------------|-----------------|  
|`UInt8`|`Number`|Windows 런타임 `Uint8`은 JavaScript 숫자로 표시되는 부호 없는 8비트 정수입니다. JavaScript 값은 먼저 JavaScript 숫자로 변환된 다음 `ToUint32` 프로세스가 수행됩니다. JavaScript 숫자 값이 Uint8의 범위를 벗어나면 결과에는 modulo 2^8이 적용됩니다.|  
|`Int32`|`Number`|Windows 런타임 `Int32`는 JavaScript 숫자로 표시되는 부호 없는 32비트 정수입니다. JavaScript 값은 먼저 JavaScript 숫자로 변환된 다음 `ToInt32` 프로세스가 수행됩니다. JavaScript 숫자 값이 `Int32`의 범위를 벗어나면 결과에는 modulo 2^16이 적용됩니다.|  
|`Int64`|`Number`|Windows 런타임 `Int64`는 부호가 있는 64비트 정수이며 [-2^53, 2^53] 범위에 속하는 경우 표준 숫자로 표시됩니다. 이 범위를 벗어나면 정수 데이터의 전체 64비트를 유지하는 사용자 지정 백업 저장소가 있는 숫자 값으로 표시됩니다. 이러한 사용자 지정 Int64 숫자 값에서 수행되는 모든 수학 연산 때문에 값이 [-2^53, 2^53] 범위의 표준 숫자로 변환됩니다. 값이 이 범위를 벗어나면 형식 오류가 발생합니다. 이 변환 프로세스의 예외는 두 개의 표시된 64비트 값을 전달할 때 전체 64비트를 기반으로 인수를 비교하는 `==`, `===`, `SameValue` 및 `RelationalComparison` 작업입니다. 두 인수 중 하나가 표준 JavaScript 숫자이면 이 작업은 비교하기 전에 인수를 JavaScript 숫자로 변환합니다. JavaScript 값이 Int64 값인 경우 자체 값이 직접 할당됩니다. 그렇지 않으면 값에 `ToInteger` 변환을 적용한 결과가 Windows 런타임에 전달됩니다. 형식 강제 변환에 실패하면 예외가 반환됩니다.|  
|`Uint64`|`Number`|Windows 런타임 `Uint64`는 부호가 없는 64비트 정수이며 [0, 2^53] 범위에 속하는 경우 표준 숫자로 표시됩니다. 이 범위를 벗어나면 부호 없는 정수 데이터의 전체 64비트를 유지하는 사용자 지정 백업 저장소가 있는 숫자로 표시됩니다. 이러한 사용자 지정 Uint64 값에서 수행되는 모든 수학 연산 때문에 값이 [0, 2^53] 범위의 표준 숫자로 변환됩니다. 값이 이 범위를 벗어나면 형식 오류가 발생합니다. 이 변환 프로세스의 예외는 두 개의 64비트 값을 전달할 때 전체 64비트를 기반으로 인수를 비교하는 `==`, `===`, `SameValue` 및 `RelationalComparison` 작업입니다. 두 인수 중 하나가 표준 JavaScript 숫자이면 이 작업은 비교하기 전에 인수를 JavaScript 숫자로 변환합니다. JavaScript 값이 Uint64 값인 경우 자체 값이 직접 할당됩니다. 그렇지 않으면 값에 `ToInteger` 변환을 적용한 후 modulo 2^52를 수행한 결과가 Windows 런타임에 전달됩니다. 형식 변환에 실패하면 예외가 반환됩니다.|  
|`Single`|`Number`|Windows 런타임 `Single`은 32비트 부동 소수점 숫자이며, 단정밀도 값과 가장 근사한 배정밀도 값을 선택하여 JavaScript 숫자로 표시됩니다. JavaScript 값은 JavaScript 숫자로 변환된 다음 값을 단정밀도 32비트 IEEE 754 부동 소수점 숫자로 표시할 수 있는지 확인하기 위해 범위 검사를 수행합니다. 변환 또는 범위 검사에 실패하면 마샬링 오류가 반환됩니다.|  
|`Double`|`Number`|Windows 런타임 `Double`은 64비트 부동 소수점 숫자입니다. `ToNumber`는 Windows 런타임 `Double`을 JavaScript 번호로 변환하는 데 사용합니다. 변환에 실패하면 마샬링 오류가 반환됩니다.|  
|`Boolean`|`Boolean`|Windows 런타임 `Boolean`은 0이 `false`이고 0이 아닌 모든 값은 `true`인 8비트 값이며 JavaScript `Boolean`로 표시됩니다. JavaScript 값은 먼저 `ToBoolean`을 사용하여 JavaScript `Boolean`로 변환됩니다. 즉, `void func(BOOL);`로 선언된 Windows 런타임 함수는 JavaScript에서 `obj.func("test");`로 작성될 수 있습니다. Windows 런타임 함수는 `TRUE`로 전달된 `BOOL` 매개 변수로 호출됩니다. 변환에 실패하면 마샬링 오류가 반환됩니다.|  
|`Char16`|`String`|Windows 런타임 `Char16`은 16비트 유니코드 문자이고, 단일 문자를 포함하는 JavaScript 문자열로 표시됩니다. JavaScript 값은 `ToString`을 통해 JavaScript 문자열로 변환된 다음 문자열의 길이가 단지 한 문자 길이인지 확인합니다. 그런 다음 단일 문자는 `Char16` 값으로 전달됩니다. 변환 또는 길이 검사에 실패하면 마샬링 오류가 반환됩니다.|  
|`String`|`String`|Windows 런타임 `String`은 변경할 수 없는 일련의 `Char16` 개체입니다. 문자열은 JavaScript `String` 개체로 표시됩니다. Windows 런타임 문자열에는 `null` 및 빈 문자열("")의 다른 값이 없습니다. `null`과 빈 문자열 값은 JavaScript 빈 문자열로 변환됩니다. 참고: JavaScript `null`을 문자열이 필요한 Windows 런타임 매개 변수에 전달하면 `null` 또는 빈 문자열("")이 아니라 문자열 값 “null”을 생성합니다. Windows 런타임에 전달된 문자열은 항상 빈 문자열로 인스턴스화해야 합니다.|  
|`Enumeration`|`Object`|Windows 런타임 `Enumeration`은 명명된 상수 집합이 연결된 32비트 정수(부호 있거나 부호가 없음)입니다. JavaScript에서 열거형은 명명된 각 값의 읽기 전용 필드를 포함하는 개체로 표시됩니다. `Int32` 및 `UInt32`에 이미 정의된 대로 열거형 값이 JavaScript 숫자로 변환됩니다. JavaScript 값을 Windows 런타임 열거형으로 변환할 때, 이전에 설명된 대로 변환하고 자르며 범위를 검사합니다. 그러나 결과 값은 열거형에 지정되어 있는 정의된 명명된 값과 비교하여 검사하지 않습니다.|  
|`Structure`|`Object`|Windows 런타임 `Structure`는 명명된 데이터 필드의 다른 컬렉션입니다. JavaScript에서 구조는 구조에 있는 각 필드의 명명된 속성을 포함하는 JavaScript 개체로 표시됩니다. 구조 값의 변환에 실패하면 마샬링 오류가 반환됩니다. Windows 런타임 구조에 동등한 필드가 없는 JavaScript 개체의 필드는 무시됩니다. 참고: Windows 런타임 구조는 JavaScript에서 `new` 키워드를 사용하여 인스턴스화될 수 없습니다.|  
|`Array`|`Array`|Windows 런타임 `Array`는 JavaScript 배열로 변환됩니다. 그러나 Windows 런타임 배열은 크기를 조정할 수 없으므로, 일부 JavaScript 배열 작업을 수행할 수 없습니다. ECMAScript 5 사양에서 허용되지 않으므로, 변환된 배열의 내부 [[Class]] 속성은 “Array”로 설정되지 않습니다. 즉, `Array.isArray(v)`에서 `false`를 반환합니다. JavaScript 값은 다음과 같이 Windows 런타임 배열로 변환됩니다. 값이 `null` 또는 `undefined`이면 네이티브 `null`로 변환됩니다. 해당 내부 [[Class]] 속성이 “Array”이면 네이티브 배열로 복사되고 이 배열의 참조가 전달됩니다. 앞서 설명한 대로 변환된 배열이 있으면 기본 네이티브 배열이 전달됩니다. 참고: JavaScript 배열 값을 Windows 런타임 메서드로 전달하면 배열의 전체 복사가 수행됩니다.|  
|대리자(함수 콜백)|`Function`|Windows 런타임 대리자는 단일 메서드에 대한 참조입니다. Windows 런타임 대리자는 JavaScript에서 JavaScript `Function`으로 표시되며, 이 함수는 적절한 스레드에서 확실히 호출됩니다. `Function`이 호출되면 인수가 해당 Windows 런타임 매개 변수 형식으로 변환됩니다. 대리자 `in` 매개 변수보다 JavaScript 인수가 적으면 대리자 호출에 실패합니다. 대리자에 있는 `in` 매개 변수보다 JavaScript 인수가 많으면 추가 JavaScript 인수가 무시됩니다. 대리자를 호출하고 나면 `out` 매개 변수가 JavaScript 형식으로 변환되고 반환됩니다. 네이티브 JavaScript 함수 개체를 Windows 런타임 대리자로 변환하고 나면 해당 형식의 Windows 런타임 대리자로 래핑됩니다. 대리자를 호출하면 `in` 매개 변수가 JavaScript 형식으로 변환됩니다. 대리자를 호출하고 나면 반환 값이 대리자의 `out` 매개 변수로 변환됩니다.|  
|인터페이스|`Object`|인터페이스 및 인터페이스 그룹은 JavaScript에서 개체로 직접 표시되지 않습니다. 그러나 인터페이스는 Windows 런타임 메서드의 매개 변수 및 반환 유형으로 표시됩니다. Windows 런타임 인터페이스 인스턴스는 다음과 같이 변환됩니다.<br /><br /> 1.  유효한 런타임 클래스가 있으면 개체를 해당 클래스의 인스턴스로 표시합니다.<br />2.  유효한 런타임 클래스가 없으면 인스턴스가 구현하는 것으로 알려진 바로 그 인터페이스와 필수 인터페이스를 구현하는 명명되지 않은 런타임 클래스의 인스턴스로 개체를 나타냅니다.<br /><br /> 런타임 클래스의 인스턴스인지 아니면 인터페이스인지를 판별하기 위해 JavaScript 값을 테스트합니다. 이 경우 원본 Windows 런타임 값에서 인터페이스를 구현하면 개체가 Windows 런타임으로 전달됩니다.|  
|런타임 클래스|`Object`|Windows 런타임의 개체는 하나 이상의 인터페이스를 구현하는 런타임 클래스의 인스턴스일 수 있습니다. Windows 런타임 개체는 JavaScript에서 개체로 표시됩니다. 클래스의 구현된 모든 인터페이스에 정의된 메서드, 속성 및 이벤트의 공용 구조체는 JavaScript 개체의 프로토타입에 명명된 속성을 나타냅니다. JavaScript 소비자는 클래스의 멤버에 직접 액세스할 수 있습니다. Windows 런타임 개체에는 런타임 클래스에 대해 구현된 모든 인터페이스의 모든 멤버를 포함하는 프로토타입이 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript에서 Windows 런타임 사용](../jswinrt/using-the-windows-runtime-in-javascript.md)
