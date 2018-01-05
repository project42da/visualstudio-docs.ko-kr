---
title: "메서드 시그니처 변경-리팩터링 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: b4f45f9d-9c8f-46ae-99f7-7705c6d90b6e
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.remove
- vs.csharp.refactoring.reorder
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: 6344a30b5772ffa23c09baa4f38a4478d907cc9e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="change-a-method-signature-in-c"></a>C# 메서드 시그니처 변경 #
**:** 메서드의 매개 변수의 순서를 변경 하거나 제거할 수 있습니다.

**경우:** 이동 하거나 다양 한 위치에서에서 현재 사용 되는 메서드 매개 변수를 제거 합니다.  

**이유:** 수도 수동으로 제거 하 고 매개 변수 순서를 변경 하 고 다음 해당 메서드에 대 한 모든 호출을 찾을 하나씩 하 여 변경할 수 있지만 오류가 발생할 수 있습니다.  이 리팩터링 도구는 자동으로 작업을 수행 합니다.

**방법:**

1. 강조 표시 하거나 수정 하는 메서드 또는 해당 사용 중 하나의 이름 내부 텍스트 커서를 놓습니다.

   ![강조 표시 된 코드](media/changesignature_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl + R**, 다음 **Ctrl + V**합니다.  바로 가기 키는 선택한 프로필에 따라 다를 수 있습니다.
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택 **시그니처 변경** 미리 보기 창 팝업에서 합니다.
   * **마우스**
     * 선택 **편집 > 리팩터링 > 매개 변수를 제거**합니다.
     * 선택 **편집 > 리팩터링 > 매개 변수 다시 정렬**합니다.
     * 코드를 마우스 오른쪽 단추로 클릭, 선택는 **빠른 작업 및 리팩터링** 메뉴와 선택 **시그니처 변경** 미리 보기 창 팝업에서 합니다.

1. 에 **서명을 변경** 대화 상자가 나타나면, 오른쪽 단추를 사용 하 여 메서드 시그니처를 변경할 수 있습니다.

   ![변경 서명 대화 상자](media/changesignature_dialog.png)

   | 단추 | 설명
   | ------ | ---
   | **위/아래로** | 선택한 매개 변수 목록 위쪽 및 아래쪽으로 이동
   | **제거**  | 목록에서 선택한 매개 변수를 제거 합니다.
   | **복원** | 목록에 복원 옵션을 선택 사선이 매개 변수

   > [!TIP]
   > 사용 하 여는 [ **참조 변경 내용 미리 보기** ](../../ide/preview-changes.md) 를 커밋하기 전에 결과 것을 확인 하려면 확인란을 선택 합니다.

1. 작업을 완료 하는 경우 키를 눌러는 **확인** 단추를 눌러 변경 내용을 합니다.

   ![변경 서명 결과](media/changesignature_result.png)

## <a name="see-also"></a>참고 항목  
[리팩터링(C#)](../refactoring-csharp.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)