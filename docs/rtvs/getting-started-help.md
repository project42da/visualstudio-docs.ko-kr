---
title: "Visual Studio용 R 도구의 도움말 창 | Microsoft Docs"
ms.custom: 
ms.date: 4/26/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef9c04d4-0d5e-405a-842e-8d47fa0e8781
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 7a873df77756e5a957d327049566c8e0db1f3a8a
ms.openlocfilehash: 6644ea68ae691e8467828ff699245fef4e485971
ms.contentlocale: ko-kr
ms.lasthandoff: 05/12/2017

---


# <a name="help-in-r-tools-for-visual-studio"></a>Visual Studio용 R 도구의 도움말

R에 대한 도움말은 Visual Studio의 대화형 창에 직접 통합됩니다. `?mtcars` 등의 `?` 명령을 사용할 때마다 R 설명서의 도움말이 Visual Studio 창에 나타납니다.

![Visual Studio의 도움말 창](~/rtvs/media/help-window.png)

> [!Tip]
> Visual Studio의 모든 다른 항목처럼 [도움말] 창을 원하는 대로 정렬 및 고정할 수 있습니다. [Visual Studio에서 창 레이아웃 사용자 지정](../ide/customizing-window-layouts-in-visual-studio.md)을 참조하세요.
>
> **R 도구 > 옵션** 메뉴를 선택하여 브라우저에서 도움말 결과를 열고 **R 도움말 브라우저** 속성을 `External`로 설정할 수도 있습니다. [옵션](options.md)을 참조하세요.

도움말을 검색하려면 `??` 명령과 함께 검색어(공백을 포함할 경우 따옴표로 묶음)를 사용합니다.

```R
??"Motor Trend"
```

![도움말 검색 결과](~/rtvs/media/help-search1.png)

[도움말] 창에는 R 설명서에서 직접 추가 검색을 수행하는 데 사용되는 검색 입력 필드도 있습니다.

![입력 필드를 사용한 도움말 검색 결과](~/rtvs/media/help-search2.png)

## <a name="integrated-help-lookup"></a>통합 도움말 조회

개발자는 종종 R 설명서에서 함수 이름, 데이터 집합 및 기타 요소에 대한 도움말을 검색하므로 Visual Studio용 R 도구에서는 도움말 조회를 편집기 및 대화형 창에 직접 통합하여 프로세스를 간소화합니다.

- 자동 완성 작업 중에 F1 키를 누르면 부분 문자열과 일치하는 도움말 결과 목록이 생성됩니다.
- 검색어(예: 함수)를 마우스 오른쪽 단추로 클릭하고 **도움말** 명령을 선택하거나, F1 키를 눌러 해당 함수에 대한 도움말을 엽니다. 선택에 대한 **도움말**을 호출할 수도 있습니다.

    ![마우스 오른쪽 단추 클릭 상황에 맞는 메뉴를 통해 도움말 호출](~/rtvs/media/help-right-click.png)

> [!Tip]
> 통합 도움말을 브라우저에서 열려면 **R 도구 > 옵션**을 선택하고 **F1 웹 브라우저**를 `External`로 설정합니다. [옵션](options.md)을 참조하세요.

## <a name="integrated-stackoverflow-search"></a>통합 StackOverflow 검색

R 설명서를 검색할 뿐 아니라 개발자는 코드를 작성하는 동안 종종 StackOverflow를 검색합니다. RTVS에서는 이 프로세스도 간소화합니다. 용어 또는 선택을 마우스 오른쪽 단추로 클릭하고 **웹에서 검색** 명령을 선택하거나 Ctrl+F1을 누르면 Visual Studio 창(또는 **F1 웹 브라우저** 옵션을 변경한 경우 브라우저)이 열리고 기본적으로 범위가 StackOverflow로 지정된 해당 용어의 검색 결과가 표시됩니다.

![Visual Studio의 웹 검색 결과](~/rtvs/media/help-web-search-results.png)

**R 도구 > 옵션 > F1 웹 검색 문자열** 옵션을 통해 추가된 문자열 `R site:stackoverflow`를 변경할 수 있습니다.

![F1 웹 검색 문자열 옵션 변경](~/rtvs/media/options-dialog.png)
