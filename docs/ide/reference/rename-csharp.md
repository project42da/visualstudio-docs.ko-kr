---
title: "C#용 Visual Studio에서 이름 바꾸기 리팩터링 | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.rename
dev_langs: CSharp
ms.workload: dotnet
ms.openlocfilehash: e1325de81e16b0e381f07af4d8073d0a3fa4330c
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="rename-a-code-symbol-in-c"></a>C#에서 코드 기호 이름 바꾸기 #

**대상:** 필드, 지역 변수, 메서드, 네임스페이스, 속성 및 형식과 같은 코드 기호의 식별자 이름을 바꿀 수 있습니다.

**시기:** 모든 인스턴스를 찾지 않고도 안전하게 이름을 바꾸고 새 이름을 복사하여 붙여넣으려고 합니다.

**이유:** 전체 프로젝트에 새 이름을 복사하여 붙여넣으면 오류가 발생할 수 있습니다.  이 리팩터링 도구는 이름 바꾸기 작업을 정확하게 수행합니다.

**방법:**

1. 이름을 바꿀 항목을 강조 표시하거나 항목 내부에 텍스트 커서를 놓습니다.

   ![강조 표시된 코드](media/rename-highlight-cs.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+R**을 누른 다음 **Ctrl+R**을 누릅니다. 바로 가기 키는 선택한 프로필에 따라 다를 수 있습니다.
   * **마우스**
     * **편집 > 리팩터링 > 이름 바꾸기**를 선택합니다.
     * 코드를 마우스 오른쪽 단추로 클릭하고 **이름 바꾸기**를 선택합니다.

1. 항목의 이름을 바꾸려면 새 이름을 입력하면 됩니다.

   ![애니메이션 이름 바꾸기](media/rename-animated-cs.gif)

   > [!TIP]
   > 또한 이 새 이름을 사용하도록 주석과 기타 문자열을 업데이트하고, IDE의 오른쪽 위에 표시되는 **이름 바꾸기** 상자의 확인란을 사용하여 저장하기 전에 [변경 내용을 미리 볼](../../ide/preview-changes.md) 수 있습니다.

1. 변경 내용에 만족할 경우 **적용** 단추를 클릭하거나 **Enter** 키를 누르면 변경 내용이 커밋됩니다.

> [!NOTE]
> 충돌을 일으키는 기존 이름을 사용할 경우 IDE의 **이름 바꾸기** 상자에 경고가 표시됩니다.
>
> ![이름 바꾸기 충돌](media/rename-conflict-cs.png)

## <a name="see-also"></a>참고 항목

[리팩터링](../refactoring-in-visual-studio.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)