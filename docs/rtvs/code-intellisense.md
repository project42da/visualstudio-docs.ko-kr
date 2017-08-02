---
title: "Visual Studio R 코드용 IntelliSense | Microsoft Docs"
ms.custom: 
ms.date: 4/28/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d96e3677-e5ec-4e11-82a8-d914a93b1aa9
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
ms.openlocfilehash: 359b9dc6bae84bb6d89e5f0f646c0b8fed5898ec
ms.contentlocale: ko-kr
ms.lasthandoff: 05/12/2017

---


# <a name="intellisense"></a>IntelliSense

Visual Studio IntelliSense를 사용하면 코드를 작성할 때 직접 보이는 곳에 호출할 수 있는 함수, 개체 멤버, 함수 인수 및 [코드 조각](code-snippets.md)에 대한 정보가 표시됩니다. 또한 입력할 때 가능한 완성이 표시되고 Tab 키나 Enter 키를 누르면 완성됩니다. **고급** 탭에 대해서는 [편집기 옵션](code-editing.md#editor-options)을 참조하세요. IntelliSense는 편집기 및 [대화형 창](interactive-repl.md)에서 둘 다 사용할 수 있습니다.

![함수 시그니처를 표시하는 IntelliSense](~/rtvs/media/intellisense-function-signature.png) 

함수나 기타 문을 입력하면 IntelliSense는 이미 입력한 내용을 기준으로 필터링된(대/소문자 구분) 자동 완성 메뉴를 제공합니다.

![IntelliSense 자동 완성 메뉴](~/rtvs/media/intellisense-auto-complete-menu.png)

Tab 키(또는 옵션 설정 방식에 따라 Enter 키 또는 Space 키)를 누르면 드롭다운에서 선택한 항목이 삽입됩니다. 화살표 키를 사용하여 선택을 변경할 수 있습니다. 

IntelliSense는 R 개체 멤버에 대한 제안도 제공합니다.
 
![개체 멤버에 대한 IntelliSense 제안](~/rtvs/media/intellisense-auto-complete-r-objects.png)
 
ESC 키를 누르면 메뉴가 완전히 닫힙니다. Ctrl+Space를 사용하여 다시 표시할 수 있습니다.

함수 호출에 대해 여는 괄호(`(`)를 입력하면 닫는 괄호(`)`)가 삽입되고 앞에서 나온 시그니처 도움말이 표시됩니다.

![함수에 대한 IntelliSense 시그니처 도움말](~/rtvs/media/intellisense-function-signature.png)

다시 ESC 키를 누르면 팝업이 닫힙니다. 함수 시그니처의 경우 Ctrl+Shift+Space를 사용하여 다시 표시할 수 있습니다.

> [!Tip]
> 매개 변수 도움말 아래 텍스트가 숨겨져 있는지 확인하려면 파일 편집기에서 할 수 있는 것처럼 Ctrl 키를 누르고 있으면 매개 변수 도움말 텍스트가 반투명하게 표시됩니다.

## <a name="intellisense-for-user-defined-functions-and-variables"></a>사용자 정의 함수 및 변수에 대한 IntelliSense

IntelliSense는 이름-매개 변수 완성을 포함하여 같은 파일의 사용자 함수에 적용됩니다.

![사용자 정의 함수에 대한 IntelliSense](~/rtvs/media/intellisense-same-file-functions.png)

![사용자 정의 함수에 대한 IntelliSense 매개 변수 완성](~/rtvs/media/intellisense-parameter-completion.png)

IntelliSense는 같은 파일 및 현재 세션의 변수에도 적용됩니다.

![IntelliSense 변수 완성](~/rtvs/media/intellisense-variable-completion.png)

> [!Note]
> 대화형 창에서 IntelliSense는 현재 R 세션의 이름만 고려하고 프로젝트의 파일을 무시합니다.

## <a name="code-suggestions"></a>코드 제안

전구(스마트 태그라고 함)가 여백에 나타나면 Visual Studio에서는 일반적으로 사용되는 작업에 사용 가능한 바로 가기를 제안합니다. 예를 들어 편집기에서 `library` 문이 포함된 줄에 커서를 올리면 전구가 표시됩니다. 전구를 선택하면 사용 가능한 옵션이 표시됩니다.

![편집기의 R용 스마트 태그](~/rtvs/media/intellisense-smart-tags.png)

