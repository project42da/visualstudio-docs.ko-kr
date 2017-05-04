---
title: "Windows 런타임 형식의 JavaScript 표현 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Windows 런타임 형식[JavaScript]"
  - "JavaScript, Windows 런타임 형식"
ms.assetid: f4851802-8b40-4afa-ba6c-8a162a9a43cc
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# Windows 런타임 형식의 JavaScript 표현
다음 표는 JavaScript에서 Windows 런타임 형식을 나타내는 방법을 설명합니다.  
  
> [!IMPORTANT]
>  Windows 런타임 기능은 Internet Explorer에서 실행되는 응용 프로그램에 사용할 수 없습니다.  
  
## JavaScript의 Windows 런타임 형식  
  
|Windows Runtime 형식|JavaScript 표현|설명|  
|------------------------|-------------------|--------|  
|`UInt8`|`Number`|Windows 런타임 `Uint8`은 JavaScript 숫자로 표현되는 부호 없는 8비트 정수입니다.  JavaScript 값이 우선 JavaScript 숫자로 변환된 다음 `ToUint32` 프로세스가 실행됩니다.  JavaScript 숫자 값이 Uint8의 범위를 벗어나는 경우 결과를 2^8으로 나눈 나머지가 적용됩니다.|  
|`Int32`|`Number`|Windows 런타임 `Int32`는 JavaScript 숫자로 표현되는 부호 있는 32비트 정수입니다.  JavaScript 값이 우선 JavaScript 숫자로 변환된 다음 `ToInt32` 프로세스가 실행됩니다.  JavaScript 숫자 값이 `Int32`의 범위를 벗어나는 경우 결과를 2^16으로 나눈 나머지가 적용됩니다.|  
|`Int64`|`Number`|Windows 런타임 `Int64`가 \[\-2^53, 2^53\] 범위 이내인 경우 표준 숫자로 표현되는 부호 있는 64비트 정수입니다.  이 범위를 벗어나면 정수 데이터의 전체 64비트를 유지하는 사용자 지정 백업 저장소가 있는 숫자 값으로 표현됩니다.  이러한 사용자 지정 Int64 숫자 값에 수학 연산을 수행하면 값이 \[\-2^53, 2^53\] 범위의 표준 숫자로 변환됩니다.  값이 이 범위를 벗어나면 형식 오류가 발생합니다.  이 변환 프로세스에 대한 예외는 두 개의 표현된 64비트 값이 전달될 때 전체 64비트를 기준으로 인수를 비교하는 `==`, `===`, `SameValue` 및 `RelationalComparison` 연산입니다.  둘 중 하나의 인수가 표준 JavaScript 숫자가 아닌 경우에도 이러한 연산은 비교 전에 해당 인수를 JavaScript 숫자로 변환합니다.  JavaScript 값 자체가 Int64 값이면 직접 할당됩니다. 그렇지 않으면 값에 `ToInteger` 변환을 적용한 결과가 Windows 런타임으로 전달됩니다.  형식 강제 변환이 실패하면 예외가 반환됩니다.|  
|`Uint64`|`Number`|Windows 런타임 `Uint64`가 \[0, 2^53\] 범위 이내인 경우 표준 숫자로 표현되는 부호 있는 64비트 정수입니다.  이 범위를 벗어나면 부호 없는 정수 데이터의 전체 64비트를 유지하는 사용자 지정 백업 저장소가 있는 숫자로 표현됩니다.  이러한 사용자 지정 Uint64 값에 수학 연산을 수행하면 값이 \[0, 2^53\] 범위의 표준 숫자로 변환됩니다.  값이 이 범위를 벗어나면 형식 오류가 발생합니다.  이 변환 프로세스에 대한 예외는 두 개의 64비트 값이 전달될 때 전체 64비트를 기준으로 인수를 비교하는 `==`, `===`, `SameValue` 및 `RelationalComparison` 연산입니다.  둘 중 하나의 인수가 표준 JavaScript 숫자가 아닌 경우에도 이러한 연산은 비교 전에 해당 인수를 JavaScript 숫자로 변환합니다.  JavaScript 값 자체가 Uint64 값이면 직접 할당됩니다. 그렇지 않으면 값에 `ToInteger` 변환을 적용한 다음 2^52로 나눈 나머지의 결과가 Windows 런타임으로 전달됩니다.  형식 변환이 실패하면 예외가 반환됩니다.|  
|`Single`|`Number`|Windows 런타임 `Single`은 단정밀도 값에 가장 가까운 배정밀도 값을 선택하여 JavaScript 숫자로 표현하는 32비트 부동 소수점 값입니다.  JavaScript 값이 JavaScript 숫자로 변환된 다음 값이 단정밀도 32비트 IEEE 754 부동 소수점 숫자로 표현될 수 있는지를 보장하기 위해 범위가 확인됩니다.  변환 또는 범위 확인이 실패하면 마샬링 오류가 반환됩니다.|  
|`Double`|`Number`|Windows 런타임 `Double` 은 64비트 부동 소수점 숫자입니다.  Windows 런타임 `Double`을 JavaScript 숫자로 변환하는 데 `ToNumber`가 사용됩니다.  변환이 실패하면 마샬링 오류가 반환됩니다.|  
|`Boolean`|`Boolean`|Windows 런타임 `Boolean`은 0이 `false`이고 0 이외의 모든 값은 `true`인 JavaScript `Boolean`로 표현되는 8비트 값입니다.  JavaScript 값이 우선 `ToBoolean`에 의해 JavaScript `Boolean`로 변환됩니다.  이는 `void func(BOOL);`로 선언된 Windows 런타임 함수는 JavaScript에서 `obj.func("test");`로 작성될 수 있다는 것을 의미합니다.  `BOOL` 매개 변수가 `TRUE`로 전달되어 Windows 런타임 함수가 호출됩니다.  변환이 실패하면 마샬링 오류가 반환됩니다.|  
|`Char16`|`String`|Windows 런타임 `Char16`은 단일 문자가 포함된 JavaScript 문자열로 표현되는 16비트 유니코드 문자입니다.  JavaScript 값이 `ToString`에 의해 JavaScript 문자열로 변환된 다음 문자열의 길이가 단일 문자인지 확인됩니다.  그런 다음 단일 문자가 `Char16` 값으로 전달됩니다.  변환 또는 길이 확인이 실패하면 마샬링 오류가 반환됩니다.|  
|`String`|`String`|Windows 런타임 `String`은 `Char16` 개체의 변경할 수 없는 시퀀스입니다.  문자열은 JavaScript `String` 개체로 표현됩니다.  Windows 런타임 문자열은 `null` 및 빈 문자열\(""\)의 값이 다르지 않습니다.  `null` 및 빈 문자열 값은 JavaScript 빈 문자열로 변환됩니다.  참고: JavaScript `null`이 문자열이어야 하는 Windows 런타임 매개 변수로 전달될 경우 `null` 또는 빈 문자열\(""\)이 아닌 "null" 문자열 값을 만듭니다.  Windows 런타임에 전달된 문자열은 항상 빈 문자열로 인스턴스화되어야 합니다.|  
|`Enumeration`|`Object`|Windows 런타임 `Enumeration`은 서로 관련 있는 명명된 상수 집합을 가진 32비트 정수\(부호 있음 또는 부호 없음\)입니다.  JavaScript에서 열거형은 각 명명된 값에 대해 읽기 전용 필드를 포함하는 개체로 표현됩니다.  열거형 값은 위에서 `Int32` 및 `UInt32`에 정의한 JavaScript 숫자로 변환됩니다.  JavaScript 값이 Windows 런타임 열거형으로 변환될 경우 변환 후 잘린 다음 위의 설명대로 범위가 확인됩니다.  하지만 결과 값은 열거형에 지정된 명명된 정의 값을 기준으로 확인되지 않습니다.|  
|`Structure`|`Object`|Windows 런타임 `Structure`는 명명된 데이터 필드의 다른 유형의 컬렉션입니다.  JavaScript에서 구조체는 구조체의 각 필드에 대한 명명된 속성을 포함하는 JavaScript 개체로 표현됩니다.  어떤 구조체 값의 변환이 실패하면 마샬링 오류가 반환됩니다.  Windows 런타임 구조체에 대응되지 않은 JavaScript 개체의 필드는 무시됩니다.  참고: Windows 런타임 구조체는 JavaScript에서 `new` 키워드로 인스턴스화할 수 없습니다.|  
|`Array`|`Array`|Windows 런타임 `Array`는 JavaScript 배열로 변환됩니다.  그러나 Windows 런타임 배열은 크기를 조정할 수 없으므로 일부 JavaScript 배열 작업은 가능하지 않습니다.  변환된 배열의 내부 \[\[클래스\]\] 속성은 ECMAScript 5 사양에서 허용되지 않으므로 "배열"로 설정되지 않습니다.  이는 `Array.isArray(v)`에서 `false`를 반환함을 의미합니다.  JavaScript 값은 Windows 런타임 배열로 변환됩니다\(값이 `null` 또는 `undefined`인 경우 네이티브 `null`로 변환됨\).  내부 \[\[클래스\]\] 속성이 "배열"이면 네이티브 배열로 복사되고 이 배열에 대한 참조가 전달됩니다.  위의 설명대로 변환된 배열인 경우에는 기본 네이티브 배열이 전달됩니다.  참고: 배열의 전체 복사를 JavaScript 배열 값은 Windows 런타임 메서드에 전달 하면 됩니다.|  
|대리자\(함수 콜백\)|`Function`|Windows 런타임 대리자는 단일 메서드에 대한 참조입니다.  Windows 런타임 대리자는 JavaScript에서 올바른 스레드에서 호출이 보장된 JavaScript `Function`으로 표현됩니다.  `Function`이 호출되면 인수가 그에 대응하는 Windows 런타임 매개 변수 형식으로 변환됩니다.  JavaScript 인수가 대리자 `in` 매개 변수보다 적으면 대리자 호출이 실패합니다.  JavaScript 인수가 대리자의 `in` 매개 변수보다 많으면 불필요한 JavaScript 인수는 무시됩니다.  대리자가 호출된 후 `out` 매개 변수는 JavaScript 형식으로 변환되어 반환됩니다.  네이티브 JavaScript 함수가 Windows 런타임 대리자로 변환되면 해당 형식의 Windows 런타임 대리자로 래핑됩니다.  대리자가 호출되면 `in` 매개 변수가 JavaScript 형식으로 변환됩니다.  대리자가 호출된 후 반환 값이 대리자의 `out` 매개 변수로 변환됩니다.|  
|인터페이스|`Object`|인터페이스 및 인터페이스 그룹은 JavaScript에서 직접 개체로 표현되지 않습니다.  그러나 인터페이스는 Windows 런타임 메서드의 매개 변수와 반환 형식으로 표현됩니다.  Windows 런타임 인터페이스 인스턴스는 다음과 같이 변환됩니다.<br /><br /> 1.  올바른 런타임 클래스가 있으면 개체를 해당 클래스의 인스턴스로 나타냅니다.<br />2.  올바른 런타임 클래스가 없으면 인스턴스가 구현하도록 지정된 인터페이스 및 요구된 인터페이스를 정확히 구현하는 명명되지 않은 런타임 클래스의 인스턴스로 개체를 표현합니다.<br /><br /> JavaScript 값을 테스트하여 런타임 클래스의 인스턴스인지 또는 인터페이스의 인스턴스인지 여부를 확인합니다.  인터페이스의 인스턴스이고 원본 Windows 런타임 값이 해당 인터페이스를 구현하면 개체가 Windows 런타임으로 전달됩니다.|  
|런타임 클래스|`Object`|Windows 런타임의 개체는 하나 이상의 인터페이스를 구현하는 런타임 클래스의 인스턴스일 수 있습니다.  Windows 런타임 개체는 JavaScript에서 개체로 표현됩니다.  클래스의 모든 구현 인터페이스에 정의된 메서드, 속성 및 클래스의 공용 구조체는 JavaScript 개체의 프로토타입에서 명명된 속성을 나타냅니다.  JavaScript 사용자는 클래스의 모든 멤버를 직접 액세스할 수 있습니다.  Windows 런타임 개체는 런타임 클래스의 모든 구현 인터페이스의 모든 멤버를 포함하는 프로토타입을 가지고 있습니다.|  
  
## 참고 항목  
 [JavaScript에서 Windows 런타임 사용](../jswinrt/using-the-windows-runtime-in-javascript.md)