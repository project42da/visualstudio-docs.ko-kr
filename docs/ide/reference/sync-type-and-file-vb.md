---
title: "Visual Basic에서 형식 및 파일 이름 동기화 | Microsoft Docs"
ms.custom: 
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: 93e1b1f446dc330b2c2c1c1e5b36e6a21e64f521
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="sync-a-type-to-a-filename-or-a-filename-to-a-type-in-visual-basic"></a>Visual Basic에서 형식을 파일 이름으로 또는 파일 이름을 형식으로 동기화

<!-- VERSIONLESS -->
**이 기능은 Visual Studio 2017 이상에서 사용할 수 있습니다.  또한 .NET Standard 프로젝트는 이 리팩터링에 대해 아직 지원되지 않습니다.**

**대상:** 파일 이름과 일치하도록 형식 이름을 바꾸거나 포함된 형식과 일치하도록 파일 이름을 바꿀 수 있습니다.

**시기:** 파일 또는 형식의 이름이 바뀌었지만 일치시킬 해당 파일 또는 형식이 업데이트되지 않았습니다. 

**이유:** 다른 이름의 파일로 형식을 저장하거나 그 반대로 저장하면 검색할 대상을 찾기 어렵습니다.  형식 또는 파일의 이름을 바꾸면 코드를 더 쉽게 읽고 탐색할 수 있습니다.

**방법:**

1. 동기화할 형식 이름을 강조 표시하거나 형식 이름 내부에 텍스트 커서를 놓습니다.

   ![강조 표시된 코드](media/synctype-highlight-vb.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+.**를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 [미리 보기] 창 팝업에서 ***TypeName*.vb로 파일 이름 바꾸기**를 선택합니다. 여기서 *TypeName*은 선택한 형식의 이름입니다.
     * **Ctrl+.**를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 [미리 보기] 창 팝업에서 **_Filename_으로 형식 이름 바꾸기**를 선택합니다. 여기서 *Filename*은 현재 파일의 이름입니다.
   * **마우스**
     * 코드를 마우스 오른쪽 단추로 클릭하고, **빠른 작업 및 리팩터링** 메뉴를 선택하고, [미리 보기] 창 팝업에서 ***TypeName*.vb로 파일 이름 바꾸기**를 선택합니다. 여기서 *TypeName*은 선택한 형식의 이름입니다.
     * 코드를 마우스 오른쪽 단추로 클릭하고, **빠른 작업 및 리팩터링** 메뉴를 선택하고, [미리 보기] 창 팝업에서 **_Filename_으로 형식 이름 바꾸기**를 선택합니다. 여기서 *Filename*은 현재 파일의 이름입니다.

   형식 또는 파일의 이름이 즉시 바뀝니다.  아래 예제에서는 **Employee.vb** 파일의 이름이 형식 이름과 일치하도록 **Person.vb**로 바뀌었습니다.

   ![인라인 결과](media/synctype-result-vb.png)

## <a name="see-also"></a>참고 항목

[리팩터링](../refactoring-in-visual-studio.md)
