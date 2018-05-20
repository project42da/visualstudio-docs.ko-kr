---
title: for 루프를 foreach 문으로 변환하는 코드 리팩터링
ms.date: 05/10/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 34758473bcbee8ccad7d9dff9df2f1478ca1202c
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
---
# <a name="refactoring-to-convert-between-a-for-loop-and-a-foreach-statement"></a>for 루프와 foreach 문 사이를 변환하는 리팩터링

이러한 리팩터링은 다음에 적용됩니다.

- C#

## <a name="convert-a-for-loop-to-a-foreach-statement"></a>for 루프를 foreach 문으로 변환

코드에 [for](/dotnet/csharp/language-reference/keywords/for) 루프가 있는 경우 이 리팩토링을 사용하여 [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) 문으로 변환할 수 있습니다.

### <a name="why-convert"></a>변환 이유

[for](/dotnet/csharp/language-reference/keywords/for) 루프를 [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) 문으로 변환하려는 이유는 다음과 같습니다.

- 항목으로 액세스하기 위한 색인을 제외하고는 루프 내에서 반복 횟수 변수를 사용하지 않으려 합니다.

- 코드를 단순화하고 초기화 프로그램, 조건 및 반복문에서 논리 오류의 가능성을 줄이려 합니다.

### <a name="how-to-use-it"></a>사용 방법

1. `for` 루프의 첫 번째 줄에 커서를 놓습니다.

1. **Ctrl**+**를 누릅니다.** 또는 코드 파일의 여백에 있는 스크루드라이버![스크루드라이버 아이콘](../media/screwdriver-icon.png) 아이콘을 클릭합니다.

   ![foreach로 변환 메뉴](media/convert-to-foreach.png)

1. **'foreach'로 변환**을 선택합니다. 또는 **변경 사항 미리 보기**를 선택하여 [변경 사항 미리 보기](../../ide/preview-changes.md) 대화 상자를 연 다음, **적용**을 선택합니다.

## <a name="convert-a-foreach-statement-to-a-for-loop"></a>foreach 문을 for 루프로 변환

코드에 [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) 문이 있는 경우 이 리팩토링을 사용하여 [for](/dotnet/csharp/language-reference/keywords/for) 루프로 변환할 수 있습니다.

### <a name="why-convert"></a>변환 이유

[foreach](/dotnet/csharp/language-reference/keywords/foreach-in) 문을 [for](/dotnet/csharp/language-reference/keywords/for) 루프로 변환하려는 이유는 다음과 같습니다.

- 항목에 단순히 액세스하는 것보다 루프 내에서 반복 횟수 변수를 사용하고자 합니다.

- [다차원 배열을 반복](/dotnet/csharp/programming-guide/arrays/using-foreach-with-arrays)하여 배열 요소에 대한 더 많은 제어권을 가지려 합니다.

### <a name="how-to-use-it"></a>사용 방법

1. `foreach` 명령의 첫 번째 줄에 커서를 놓습니다.

1. 줄의 임의 위치에서 **Ctrl**+**.** 를 눌러 또는 코드 파일의 여백에 있는 스크루드라이버![스크루드라이버 아이콘](../media/screwdriver-icon.png) 아이콘을 클릭합니다.

   ![for로 변환 메뉴](media/convert-to-for.png)

1. **'for'로 변환**을 선택합니다. 또는 **변경 사항 미리 보기**를 선택하여 [변경 사항 미리 보기](../../ide/preview-changes.md) 대화 상자를 연 다음, **적용**을 선택합니다.

1. 리팩터링이 새로운 반복 횟수 변수를 도입하기 때문에 **이름 바꾸기** 상자가 편집기의 오른쪽 상단에 나타납니다. 변수에 다른 이름을 선택하려면 여기에 입력한 다음, **Enter**를 누르거나 **이름 바꾸기** 상자에서 **적용**을 선택합니다. 새 이름을 선택하지 않으려면 **Esc**를 누르거나 **적용**을 선택하여 **이름 바꾸기** 상자를 닫습니다.

## <a name="see-also"></a>참고 항목

- [리팩터링](../refactoring-in-visual-studio.md)
- [변경 내용 미리 보기](../../ide/preview-changes.md)