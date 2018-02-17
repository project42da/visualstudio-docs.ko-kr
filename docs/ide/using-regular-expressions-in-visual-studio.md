---
title: "Visual Studio에서 정규식 사용 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vsregularexpressionhelp
- vs.regularexpressionhelp
- vs.wildcardsbuilder
- vs.netregularexpressionhelp
- vs.wildcards
helpviewer_keywords:
- regular expressions [Visual Studio]
- regular expressions
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 077bb266e6ed55bfe59ec4e537b516ccde59e0c3
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="using-regular-expressions-in-visual-studio"></a>Visual Studio에서 정규식 사용

Visual Studio에서는 [.NET Framework 정규식](/dotnet/standard/base-types/regular-expressions)을 사용하여 텍스트를 찾고 바꿉니다.

## <a name="replacement-patterns"></a>대체 패턴

바꾸기 패턴에서 사용되는 정규식에 대한 자세한 내용은 [정규식의 대체(.NET 가이드)](/dotnet/standard/base-types/substitutions-in-regular-expressions)를 참조하세요. 번호가 있는 캡처 그룹을 사용하려는 경우 번호가 있는 그룹을 지정하려면 `$1` 구문을 사용하고 특정 그룹을 지정하려면 `(x)` 구문을 사용합니다. 예를 들어 그룹화된 정규식 `(\d)([a-z])`는 문자열 **1a 2b 3c 4d**에서 일치 항목 4개를 찾습니다. 바꾸기 문자열 `z$1`은 해당 문자열을 **z1 z2 z3 z4**로 변환합니다.

## <a name="regular-expression-examples"></a>정규식 예제

다음은 몇 가지 예입니다.

|용도|식|예|
|-------------|----------------|-------------|
|줄 바꿈 이외의 모든 단일 문자를 찾습니다.|이어야 합니다.|`a.o`는 "around"의 "aro" 및 "about"의 "abo"와 일치하지만 "across"의 "acro"와 일치하지 않습니다.|
|이전 식에서 일치 항목 0개 이상을 찾습니다(가능한 한 많은 문자를 찾음).|*|`a*r`는 "rack"의 "r", "ark"의 "ar", "aardvark"의 "aar"과 일치합니다.|
|임의의 문자를 0회 이상 찾습니다(와일드카드 *).|.*|c.*e는 “racket”의 “cke”, “comment”의 “comme”, “code”의 “code”와 일치합니다.|
|이전 식에서 일치 항목 1개 이상을 찾습니다(가능한 한 많은 문자를 찾음).|+|`e.+e`는 "feeder"의 "eede"와 일치하지만 "ee"와 일치하지 않습니다.|
|임의의 문자를 1회 이상 찾습니다(와일드카드 ?).|.+|e.+e는 "feeder"의 "eede"와 일치하지만 "ee"와 일치하지 않습니다.|
|이전 식에서 일치 항목 0개 이상을 찾습니다(가능한 한 적은 문자를 찾음).|*?|`e.*?e`는 "feeder"의 "ee"와 일치하지만 "eede"와 일치하지 않습니다.|
|이전 식에서 일치 항목 1개 이상을 찾습니다(가능한 한 적은 문자를 찾음).|+?|`e.+?e`는 "enterprise"의 "ente" 및 "erprise"와 일치하지만 전체 단어 "enterprise"와 일치하지 않습니다.|
|일치 문자열을 줄 또는 문자열의 시작에 고정합니다.|^|`^car`는 줄의 시작 부분에 나타날 때만 단어 "car"와 일치합니다.|
|일치 문자열을 줄의 끝에 고정합니다.|\r?$|`End\r?$`는 줄의 끝 부분에 나타날 때만 단어 "end"와 일치합니다.|
|집합에 있는 단일 문자를 찾습니다.|[abc]|`b[abc]`는 "ba", "bb", "bc"와 일치합니다.|
|문자 범위에서 임의 문자를 찾습니다.|[a-f]|`be[n-t]`는 "between"의 "bet", "beneath"의 "ben", "beside"의 "bes"와 일치하지만 "below"와 일치하지 않습니다.|
|괄호 안에 포함된 식을 캡처하고 명시적으로 번호를 지정합니다.|()|`([a-z])X\1`은 "aXa" 및 "bXb"와 일치하지만 "aXb"와 일치하지 않습니다. " ". “\1”은 첫 번째 식 그룹 “[a-z]”를 나타냅니다.|
|일치를 무효화합니다.|(?!abc)|`real (?!ity)`는 "realty" 및 "really"의 "real"과 일치하지만 "reality"와 일치하지 않습니다. "realityreal"에서 두 번째 "real"도 찾지만 첫 번째 "real"은 찾지 않습니다.|
|지정된 문자 집합에 없는 모든 문자를 찾습니다.|[^abc]|`be[^n-t]`는 "before"의 "bef", "behind"의 "beh", "below"의 "bel"과 일치하지만 "beneath"와 일치하지 않습니다.|
|기호 앞 또는 기호 뒤에 있는 식을 찾습니다.|&#124;|`(sponge&#124;mud) bath`는 "sponge bath" 및 "mud bath"와 일치합니다.|
|백슬래시 뒤의 문자를 이스케이프합니다.|\\|`\^`은 문자 ^과 일치합니다.|
|이전 문자 또는 그룹의 일치 항목 수를 지정합니다.|{x}. 여기서 x는 일치 항목 수입니다.|`x(ab){2}x`는 "xababx"와 일치하고, `x(ab){2,3}x`는 "xababx" 및 "xabababx"와 일치하지만 "xababababx"와 일치하지 않습니다.|
|유니코드 문자 클래스에서 텍스트를 찾습니다. 여기서 “X”는 유니코드 번호입니다. 유니코드 문자 클래스에 대한 자세한 내용은<br /><br /> [Unicode Standard 5.2 Character Properties](http://www.unicode.org/versions/Unicode5.2.0/ch04.pdf)(유니코드 표준 5.2 문자 속성)를 참조하세요.|\p{X}|`\p{Lu}`는 "Thomas Doe"의 "T" 및 "D"와 일치합니다.|
|단어 경계를 찾습니다.|`\b`(\b는 문자 클래스 외부에서 단어 경계를 지정하고 문자 클래스 내부에서 백스페이스를 지정함).|`\bin`은 "inside"의 "in"과 일치하지만 "pinto"와 일치하지 않습니다.|
|줄 바꿈을 찾습니다(캐리지 리턴 뒤에 줄 바꿈).|\r?\n|`End\r?\nBegin`은 "End"가 줄의 마지막 문자열이고 "Begin"이 다음 줄의 첫 번째 문자열일 때만 "End" 및 "Begin"과 일치합니다.|
|영숫자 문자를 찾습니다.|\w|`a\wd`는 "add" 및 "a1d"와 일치하지만 "a d"와 일치하지 않습니다.|
|공백 문자를 찾습니다.|(?([^\r\n])\s)|`Public\sInterface`는 구 "Public Interface"와 일치합니다.|
|임의 숫자 문자를 찾습니다.|\d|`\d`는 "3456"의 "3", 23"의 "2", "1"의 "1"과 일치합니다.|
|유니코드 문자를 찾습니다.|\uXXXX. 여기서 XXXX는 유니코드 문자 값을 지정합니다.|`\u0065`는 문자 "e"와 일치합니다.|
|식별자를 찾습니다.|\b(_\w+&#124;[\w-[0-9\_]]\w*)\b|“type1"과 일치하지만 &type1" 또는 "#define"과 일치하지 않습니다.|
|따옴표 안의 문자열을 찾습니다.|((\\".+?\\")&#124;('.+?'))|작은따옴표 또는 큰따옴표 안의 문자열을 찾습니다.|
|16진수를 찾습니다.|\b0[xX]([0-9a-fA-F]\)\b|"0xc67f"와 일치하지만 "0xc67fc67f"와 일치하지 않습니다.|
|정수 및 소수를 찾습니다.|\b[0-9]*\\.\*[0-9]+\b|"1.333"과 일치합니다.|

> [!TIP]
> Windows 운영 체제에서 대부분 줄은 “\r\n”(캐리지 리턴 뒤에 줄 바꿈)으로 끝납니다. 이들 문자는 표시되지 않지만 편집기에 있고 .NET 정규식 서비스에 전달됩니다.

## <a name="see-also"></a>참고 항목

[텍스트 찾기 및 바꾸기](../ide/finding-and-replacing-text.md)