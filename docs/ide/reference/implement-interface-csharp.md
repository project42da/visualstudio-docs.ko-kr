---
title: "인터페이스 구현 - 코드 생성(C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bebff2ad-25b6-4adc-8762-60d23bdd639a
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 908e11da78b2a83fb3da23d28b5cc52613f7b0f2
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2018
---
# <a name="implement-an-interface-in-c"></a>C#에서 인터페이스 구현 #
**대상:** 인터페이스를 구현하는 데 필요한 코드를 즉시 생성할 수 있습니다. 

**시기:** 인터페이스에서 상속하려고 합니다.  

**이유:** 모든 인터페이스를 하나씩 수동으로 구현할 수 있지만 이 기능은 모든 메서드 시그니처를 자동으로 생성합니다. 

**방법:**

1. 인터페이스를 참조했지만 모든 필요한 멤버를 구현하지 않았음을 나타내는 빨간색 구부러진 곡선이 있는 줄에 커서를 놓습니다.

   ![강조 표시된 코드](media/interface-highlight-cs.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+.**를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 [미리 보기] 창 팝업에서 **인터페이스 구현(명시적)**을 선택합니다.
   * **마우스**
     * 마우스 오른쪽 단추를 클릭하고, **빠른 작업 및 리팩터링** 메뉴를 선택하고, [미리 보기] 창 팝업에서 **인터페이스 구현(명시적)**을 선택합니다.
     * 빨간색 구부러진 곡선 위로 마우스를 이동하고 표시되는 ![전구](media/bulb-cs.png) 아이콘을 클릭합니다.
     * 텍스트 커서가 이미 구부러진 빨간 곡선이 있는 줄 위에 있으면 왼쪽 여백에 나타나는 ![전구](media/bulb-cs.png) 아이콘을 클릭합니다.

   ![클래스 구현 미리 보기](media/interface-preview-cs.png)

   >[!TIP]
   >미리 보기 창 맨 아래에 있는 [**변경 내용 미리 보기**](../../ide/preview-changes.md) 링크를 사용하여 선택하기 전에 적용될 모든 변경 내용을 확인합니다.
   >
   >또한 미리 보기 창의 맨 아래에 있는 **문서**, **프로젝트** 및 **솔루션** 링크를 사용하여 인터페이스를 구현하는 여러 클래스에서 적절한 메서드 시그니처를 만들 수 있습니다.

1. 인터페이스의 메서드 시그니처가 자동으로 만들어지고 구현할 준비가 됩니다.

   ![클래스 구현 결과](media/interface-result-cs.png)

   >[!TIP]
   >이름 충돌을 방지하려면 **명시적으로 인터페이스 구현** 옵션을 사용하여 생성된 각 메서드 앞에 인터페이스 이름을 추가합니다.
   >
   >![명시적으로 인터페이스 구현 결과](media/interface-explicitresult-cs.png); 

## <a name="see-also"></a>참고 항목

[코드 생성](../code-generation-in-visual-studio.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)  
