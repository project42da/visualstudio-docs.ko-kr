---
title: "Visual Studio용 Python 도구에서 코드 편집 | Microsoft Docs"
ms.custom: 
ms.date: 3/7/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03effe56-d6f6-461d-9005-e43c15bf537c
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
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
ms.sourcegitcommit: a42f5a30375192c89c9984e40ba0104da98d7253
ms.openlocfilehash: 79d7c18b672119b745258feee0f646dff96c1922
ms.lasthandoff: 03/07/2017

---

# <a name="editing-python-code"></a>Python 코드 편집

개발자는 코드 편집기에서 많은 시간을 보내기 때문에 PTVS(Visual Studio용 Python 도구)에서 IntelliSense 구문 강조 표시, 자동 완성, 서명 도움말, 메서드 재정의/검색 및 탐색과 같은 생산성 향상에 도움이 되는 기능을 제공합니다. 

항목 내용:

- [IntelliSense](#intellisense)(완성, 서명 도움말, 요약 정보 및 코드 색 지정 등을 포함)
- [코드 조각](#code-snippets)
- [코드 탐색](#navigating-your-code)

Visual Studio에서 코드 편집에 대한 일반적 설명서는 [코드 및 텍스트 편집기에서 코드 작성](../ide/writing-code-in-the-code-and-text-editor.md)을 참조하세요. 또한 코드의 특정 섹션에 집중하는 데 도움이 되는 [Visual Studio 개요](../ide/outlining.md)도 참조하세요. PTVS는 각 모듈에 정의된 클래스와 이 클래스에 정의된 함수를 검사하기 위해 Visual Studio 개체 브라우저(**보기 > 다른 창 > 개체 브라우저** 또는 Ctrl+W, J)를 통해 지원합니다. 

Python 코드 편집에 대한 소개는 다음 [PTVS 시작 3부: 편집](https://youtu.be/uZGZNEyyeKs?list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff)(youtube.com, 3분 48초)를 참조하세요.

> [!VIDEO https://www.youtube.com/embed/uZGZNEyyeKs]

## <a name="intellisense"></a>IntelliSense

IntelliSense는 [완성](#completions), [서명 도움말](#signature-help), [요약 정보](#quick-info) 및 [코드 색 지정](#code-coloring)을 제공합니다. IntelliSense는 프로젝트의 각 Python 환경에 대해 생성된 완성 데이터베이스를 통해 성능을 향상시킵니다. 패키지를 추가, 제거 또는 업데이트하고 **Python 환경** 창(솔루션 탐색기의 형제)의 **IntelliSense** 탭에 상태가 표시되면, 데이터베이스를 새로 고쳐야 할 수도 있습니다([Python 환경](python-environments.md) 참조). 

### <a name="completions"></a>완성

완성은 문, 식별자 및 편집기의 현재 위치에 적절히 입력될 수 있는 다른 단어로 표시됩니다. 목록에 표시된 내용은 컨텍스트를 기반으로 하며, 잘못되었거나 불필요한 옵션을 생략하도록 필터링됩니다. 완성은 종종 다른 문(예: `import`) 및 연산자(마침표 포함)를 입력하여 트리거되지만, 언제든지 Ctrl+J, 스페이스를 입력하여 표시되도록 할 수 있습니다.

![멤버 완성](media/code-editing-completions-simple.png)

완성 목록이 열리면 화살표 키와 마우스를 사용하거나 계속 입력하여 원하는 완성을 검색할 수 있습니다. 더 많은 글자를 입력함에 따라 목록이 자세히 필터링되어 더 확실한 완성을 보여 줍니다. 이 필터링은 스마트 기능이며, 다음과 같은 바로 가기를 사용할 수 있게 합니다.

- 'parse'와 같이 이름의 시작 부분에 없는 글자를 입력하면 'argparse'를 찾습니다.
- 'abc'와 같이 단어의 시작 부분에 있는 글자만 입력하면 'AbstractBaseClass'를 찾거나 'air'를 입력하면 'as_integer_ratio'를 찾습니다.
- 'b64'와 같이 문자를 건너뛰면 'base64'를 찾습니다.

몇 가지 예:

![필터링을 통한 멤버 완성](media/code-editing-completion-filtering.png)

변수 또는 값 뒤에 마침표를 입력하면 멤버 완성이 자동으로 표시되고, 잠재적인 형식의 메서드와 특성이 표시됩니다. 변수가 둘 이상의 형식일 수 있는 경우 목록에는 모든 형식의 모든 가능성 및 각 완성을 지원하는 형식을 나타내는 추가 정보가 포함됩니다. 완성이 가능한 모든 형식으로 지원되는 경우 주석 없이 표시됩니다.

![여러 형식의 멤버 완성](media/code-editing-completion-types.png)

기본적으로 겹밑줄(double underscore)로 시작하고 끝나는 멤버는 표시되지 않습니다. 일반적으로 이러한 멤버를 직접 액세스하면 안되지만, 필요한 경우 다음과 같이 선행 겹밑줄을 입력하면 이러한 완성이 목록에 추가됩니다.

![전용 멤버 완성](media/code-editing-completion-dunder.png)

`import` 및 `from ... import` 문은 가져올 수 있는 모듈의 목록을 표시하고, `from ... import`의 경우에는 지정된 모듈에서 가져올 수 있는 멤버를 표시합니다.

![가져오기 완성](media/code-editing-completion-import.png)

`raise` 및 `except` 문은 오류 형식이 될 수 있는 클래스의 목록을 표시합니다. 여기서는 모든 사용자 정의 예외가 포함되지는 않지만, 적합한 기본 제공 예외를 빠르게 찾을 수 있습니다.

![예외 완성](media/code-editing-completion-exception.png)

@를 입력하면 데코레이터가 시작되고, 잠재적 데코레이터가 표시됩니다. 이러한 항목 중 많은 항목은 데코레이터로 사용할 수 없으므로 라이브러리 설명서를 확인하여 사용할 항목을 결정해야 합니다.

![데코레이터 완성](media/code-editing-completion-decorator.png)

> [!Tip]
> **도구 > 옵션 > 텍스트 편집기 > Python > 고급**을 통해 완성 동작을 구성할 수 있습니다. 여기서 **검색 문자열 기준 필터 목록**은 입력 시 완성 제안 필터링을 적용하며(기본적으로 선택한 상태), **멤버 완성에서 멤버 교집합 표시**는 가능한 모든 형식에서 지원되는 완성만 표시합니다(기본적으로 선택 취소됨).


### <a name="signature-help"></a>서명 도움말

함수를 호출하는 코드를 작성할 때 여는 `(`를 입력하면 서명 도움말이 표시되며, 사용할 수 있는 모든 설명서와 매개 변수 정보를 보여 줍니다. 또한 함수 호출 내에서 Ctrl+Shift+스페이스를 사용하여 표시할 수도 있습니다. 표시되는 정보는 함수의 원본 코드에 있는 설명서 문자열에 따라 다르지만 모든 기본값이 포함됩니다.

![서명 도움말](media/code-editing-signature-help.png)

> [!Tip]
> 서명 도움말을 사용하지 않으려면 **도구 > 옵션 > 텍스트 편집기 > Python > 일반**으로 이동하여 **문 완성 > 매개 변수 정보**를 선택 취소합니다.

### <a name="quick-info"></a>요약 정보

식별자 위로 마우스 포인터를 가져가면 요약 정보 도구 설명이 표시됩니다. 식별자에 따라 요약 정보는 잠재적인 값이나 형식, 사용 가능한 모든 설명서, 반환 형식 및 정의 위치를 표시할 수 있습니다.

![요약 정보](media/code-editing-quick-info.png)

### <a name="code-coloring"></a>코드 색 지정

코드 색 지정은 코드 분석에서 색 변수, 문 및 코드의 다른 부분에 이르는 정보를 사용합니다. 예를 들어 모듈이나 클래스를 참조하는 변수는 함수 또는 다른 값과 다른 색으로 표시될 수 있으며, 매개 변수 이름은 지역 변수 또는 전역 변수와 다른 색으로 표시됩니다(함수는 기본적으로 굵게 표시되지 않음).

![코드 색 지정](media/code-editing-code-coloring.png)

사용되는 색을 사용자 지정하려면 **도구 > 옵션 > 환경 > 글꼴 및 색**으로 이동하여 **항목 표시** 목록에서 Python 항목을 수정합니다.

![글꼴 및 색 옵션](media/code-editing-customize-colors.png)

> [!Tip]
> 코드 색 지정을 사용하지 않으려면 **도구 > 옵션 > 텍스트 편집기 > Python > 고급**으로 이동하여 **기타 옵션 > 형식별 색 이름**을 선택 취소합니다.

## <a name="code-snippets"></a>코드 조각

코드 조각은 바로 가기를 입력하고 Tab 키를 누르거나 **편집 > IntelliSense > 코드 조각 삽입** **코드 감싸기** 명령을 사용하여 파일에 삽입할 수 있는 코드의 부분입니다. 예를 들어 `class` 다음에 Tab 키를 입력하면 클래스의 나머지 부분이 생성됩니다. 이름과 베이스 목록을 입력하고, Tab 키를 사용하여 강조 표시된 필드 사이를 이동한 다음, Enter 키를 눌러 본문을 입력할 수 있습니다.

![코드 조각](media/code-editing-code-snippets.png)

언어로 **Python**을 선택하여 코드 조각 관리자(**도구 > 코드 조각 관리자**)에서 사용 가능한 코드 조각을 볼 수 있습니다.

![코드 조각 관리자](media/code-editing-code-snippets-manager.png)

사용자 고유의 코드 조각을 만들려면 [연습: 코드 조각 만들기](https://docs.microsoft.com/en-us/visualstudio/ide/walkthrough-creating-a-code-snippet)를 참조하세요.
코드 조각은 [코드 조각을 만들고](https://msdn.microsoft.com/en-us/library/ms165394.aspx) 이를 가져와서 사용자 지정할 수 있습니다. 

공유하려는 중요한 코드 조각을 작성하는 경우 자유롭게 요점에 게시하고 [알려주세요](https://github.com/Microsoft/PTVS/issues). 그러면 PTVS의 향후 릴리스에 포함할 수 있습니다.


## <a name="navigating-your-code"></a>코드 탐색

PTVS는 원본 코드를 사용할 수 있는 라이브러리, 즉 [탐색 모음](#navigation-bar), [정의로 이동](#go-to-definition), [다음 탐색](#navigate-to), [모든 참조 찾기](#find-all-references) 및 [개체 브라우저](#object-browser)를 포함하여 코드 내에서 빠르게 탐색할 수 있는 여러 가지 수단을 제공합니다.

### <a name="navigation-bar"></a>탐색 모음

탐색 모음은 각 편집기 창의 위쪽에 표시되며, 정의의&2;단계 목록을 포함하고 있습니다. 왼쪽 드롭다운에서는 현재 파일의 최상위 클래스와 함수 정의를 포함하고 있으며, 오른쪽 드롭다운에서는 왼쪽에 표시된 범위 내의 정의 목록을 표시합니다. 편집기에서 이동하는 대로 업데이트하여 현재 컨텍스트를 보여 주며, 이러한 목록에서 항목을 선택하여 직접 이동할 수도 있습니다.

![탐색 모음](media/code-editing-navigation-bar.png)

> [!Tip]
> 탐색 모음을 숨기려면 **도구 > 옵션 > 텍스트 편집기 > Python > 일반**으로 이동하여 **설정 > 탐색 모음**을 선택 취소합니다.

### <a name="go-to-definition"></a>정의로 이동

**정의로 이동**은 식별자(예: 함수 이름, 클래스 또는 변수)를 사용하여 정의된 원본 코드로 빠르게 이동합니다. 정의를 호출하려면 식별자를 마우스 오른쪽 단추로 클릭하여 **정의로 이동**을 선택하거나 식별자에 캐럿을 배치하고 F12 키를 누릅니다. 원본 코드를 사용할 수 있는 경우 코드 및 외부 라이브러리에서 작동합니다. 라이브러리 원본 코드를 사용할 수 없는 경우 **정의로 이동**은 모듈 참조를 위해 관련 `import` 문으로 건너뛰거나 오류를 표시합니다.

![정의로 이동](media/code-editing-go-to-definition.png)

### <a name="navigate-to"></a>다음 탐색

**편집 > 다음 탐색...** 명령(Ctrl+,)은 문자열을 입력하고 해당 문자열을 포함하는 함수, 클래스 또는 변수를 정의하는 코드에서 가능한 일치 항목을 볼 수 있는 검색 상자를 편집기에 표시합니다. 이는 **정의로 이동**과 비슷한 기능을 제공하지만 식별자를 사용하여 찾을 필요가 없습니다.

이름을 두 번 클릭하거나 화살표 키로 선택하고 Enter 키를 누르면 해당 식별자의 정의로 이동합니다.

![다음 탐색](media/code-editing-navigate-to.png)

### <a name="find-all-references"></a>모든 참조 찾기

**모든 참조 찾기**는 가져오기 및 할당을 포함하여 지정된 식별자가 정의되고 사용되는 위치를 찾는 유용한 방법입니다. 참조를 호출하려면 식별자를 마우스 오른쪽 단추로 클릭하여 **모든 참조 찾기**을 선택하거나 식별자에 캐럿을 배치하고 Shift+F12를 누릅니다. 목록에서 항목을 두 번 클릭하면 해당 위치로 이동합니다.

![모든 참조 찾기 결과](media/code-editing-find-all-references.png)
