---
title: "재정의 생성 - 코드 생성(Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c8cfc4-7c1f-4606-970e-3f7651604bab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 334f5a79dad1b7d2c14768d0698797a34ad039c5
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2018
---
# <a name="generate-an-override-in-visual-basic"></a>Visual Basic에서 재정의 생성
**대상:** 기본 클래스에서 재정의할 수 있는 메서드에 대한 코드를 즉시 생성할 수 있습니다. 

**시기:** 기본 클래스 메서드를 재정의하고 시그니처를 자동으로 생성하려고 합니다.  

**이유:** 메서드 시그니처를 직접 작성할 수 있지만 이 기능은 시그니처를 자동으로 생성합니다. 

**방법:**

1. **Overrides** 키워드, 공백을 차례로 입력합니다. 이 위치에 재정의된 메서드 시그니처를 삽입할 수 있고 IntelliSense 드롭다운이 나타납니다.

   ![IntelliSense 재정의](media/override-intellisense-vb.png)

1. 기본 클래스에서 재정의할 메서드를 마우스로 클릭하거나 키보드에서 **Enter** 키를 눌러 메서드로 이동하여 메서드를 선택합니다.

<!--
   >[!TIP]
   >* Use the Property icon ![Property icon](media/override-property-vb.png) to show or hide  Properties in the list.
   >* Use the Method icon ![Property icon](media/override-method-vb.png) to show or hide Methods in the list.
-->

1. 선택한 메서드 또는 속성이 구현할 수 있는 재정의로 클래스에 추가됩니다.

   ![재정의 결과](media/override-result-vb.png)

## <a name="see-also"></a>참고 항목

[코드 생성](../code-generation-in-visual-studio.md) 