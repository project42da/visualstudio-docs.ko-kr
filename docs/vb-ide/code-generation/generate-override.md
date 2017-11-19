---
title: "재정의-코드 생성 (Visual Basic)를 생성 | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c8cfc4-7c1f-4606-970e-3f7651604bab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e8a7658ff8e2f573f2da6ff3197b6a11f3b3a0a7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="generate-an-override-in-visual-basic"></a>Visual Basic에서는 재정의 생성 합니다.
**:** 즉시 기본 클래스에서 재정의 될 수 있는 모든 메서드에 대 한 코드를 생성할 수 있습니다. 

**경우:** 기본 클래스 메서드를 재정의 하 여 서명을 자동으로 생성 합니다.  

**이유:** 작성할 수 메서드 시그니처를 직접 있지만이 기능은 서명을 자동으로 생성 됩니다. 

**방법:**

1. 형식에서 **재정의** 키워드, 공백, 여기서 재정의 된 메서드 시그니처를 삽입 하려고 하 고 IntelliSense 드롭다운이 표시 됩니다.

   ![IntelliSense를 재정의 합니다.](media/override_intellisense.png)

1. 마우스 클릭 또는 키보드와 키를 눌러 탐색 하 여 기본 클래스에서 재정의 하려는 방법을 선택 **Enter**합니다.

<!--
   >[!TIP]
   >* Use the Property icon ![Property icon](media/override_property.png) to show or hide  Properties in the list.
   >* Use the Method icon ![Property icon](media/override_method.png) to show or hide Methods in the list.
-->

1. 선택한 메서드 또는 속성은 재정의 구현할 준비가로 클래스에 추가 됩니다.

   ![결과 재정의 합니다.](media/override_result.png)

## <a name="see-also"></a>참고 항목  
[코드 생성(Visual Basic)](../code-generation-vb.md) 