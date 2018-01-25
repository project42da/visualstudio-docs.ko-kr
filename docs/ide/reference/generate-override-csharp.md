---
title: "재정의 생성 - 코드 생성(C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c8cfc4-7c1f-4606-970e-3f7651604bab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 3801d8ce60cf87126f8894bf44c77056f996cde1
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="generate-an-override-in-c"></a>C#에서 재정의 생성 #

**대상:** 기본 클래스에서 재정의할 수 있는 메서드에 대한 코드를 즉시 생성할 수 있습니다.

**시기:** 기본 클래스 메서드를 재정의하고 시그니처를 자동으로 생성하려고 합니다.

**이유:** 메서드 시그니처를 직접 작성할 수 있지만 이 기능은 시그니처를 자동으로 생성합니다.

**방법:**

1. **override** 키워드, 공백을 차례로 입력합니다. 이 위치에 재정의된 메서드 시그니처를 삽입할 수 있고 IntelliSense 드롭다운이 나타납니다.

   ![IntelliSense 재정의](media/override-intellisense-cs.png)

1. 기본 클래스에서 재정의할 메서드를 마우스로 클릭하거나 키보드에서 **Enter** 키를 눌러 메서드로 이동하여 메서드를 선택합니다.

   >[!TIP]
   >* 속성 아이콘 사용 ![속성 아이콘](media/override-property-cs.png) 목록에서 속성을 표시하거나 숨깁니다.
   >* 메서드 아이콘 사용 ![메서드 아이콘](media/override-method-cs.png) 목록에서 메서드를 표시하거나 숨깁니다.

1. 선택한 메서드 또는 속성이 구현할 수 있는 재정의로 클래스에 추가됩니다.

   ![재정의 결과](media/override-result-cs.png)

## <a name="see-also"></a>참고 항목

[코드 생성](../code-generation-in-visual-studio.md)
