---
title: 빠른 작업 | Microsoft 문서
ms.date: 03/28/2018
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 941980eff8fc2474df9555b326278abdb9b26dac
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="quick-actions"></a>빠른 작업

빠른 작업을 사용하면 단일 작업으로 쉽게 코드를 리팩터링하거나, 생성하거나, 수정할 수 있습니다. 빠른 작업은 C#, [C++](/cpp/ide/writing-and-refactoring-code-cpp) 및 Visual Basic 코드 파일에 사용할 수 있습니다. 일부 작업은 특정 언어에 국한되며, 나머지 작업은 모든 언어에 적용됩니다.

빠른 작업은 다음에 사용할 수 있습니다.

- [코드 분석기](../code-quality/roslyn-analyzers-overview.md) 규칙 위반에 대한 코드 수정 적용
- 코드 분석기 규칙 위반 [표시 안 함](../code-quality/use-roslyn-analyzers.md)
- 리팩터링 적용(예: [임시 변수 인라인](../ide/reference/inline-temporary-variable.md))
- 코드 생성(예: [지역 변수 도입](../ide/reference/introduce-local-variable.md))

빠른 작업은 전구 아이콘 ![작은 전구 아이콘](media/vs2015_lightbulbsmall.png)을 사용하거나 **Ctrl**+**.** 를 눌러 적용할 수 있습니다. 동작을 사용할 수 있는 코드 줄에 커서가 있는 경우입니다. 빨간색 오류 표시선이 나타나는 경우 전구가 표시되며 Visual Studio에서는 문제 해결 방법에 대한 제안이 나타납니다. 예를 들어 빨간색 오류 표시선으로 나타난 오류가 있는 경우 해당 오류에 대한 해결 방법을 사용할 수 있을 때 전구가 나타납니다.

어떤 언어든지 타사에서 SDK에 포함하는 방식 등을 통해 사용자 지정 진단 및 제안을 제공할 수 있으며 Visual Studio 전구는 이러한 규칙을 기반으로 켜집니다.

## <a name="to-see-a-light-bulb"></a>전구를 표시하려면

1. 대부분의 경우 전구는 오류 지점에 마우스를 가져갈 때 자연스럽게 나타나거나 오류가 포함된 줄로 캐럿을 이동할 때 편집기의 왼쪽 여백에 자동으로 나타납니다. 빨간색 오류 표시선이 보이면 마우스로 가리켜 전구를 표시할 수 있습니다. 줄에서 오류가 발생한 위치로 이동하기 위해 마우스나 키보드를 사용할 때 전구가 표시되도록 할 수도 있습니다.

1. 줄의 임의 위치에서 **Ctrl**+**.** 를 눌러 줄의 임의 위치를 눌러 전구를 호출하고 잠재적 해결 방법 목록으로 바로 이동합니다.

   ![마우스로 가리킨 전구](../ide/media/vs2015_lightbulb_hover.png)

## <a name="to-see-potential-fixes"></a>잠재적 해결 방법을 보려면

아래쪽 화살표나 잠재적 해결 방법 표시 링크를 클릭하여 전구가 수행할 수 있는 빠른 작업 목록을 표시합니다.

![확장된 전구](../ide/media/vs2015_lightbulb_hover_expanded.png)

## <a name="see-also"></a>참고 항목

- [Visual Studio에서 코드 생성](../ide/code-generation-in-visual-studio.md)
- [일반적인 빠른 작업](../ide/common-quick-actions.md)
- [코드 스타일 및 빠른 작업](../ide/code-styles-and-quick-actions.md)
- [코드 작성 및 리팩터링(C++)](/cpp/ide/writing-and-refactoring-code-cpp)