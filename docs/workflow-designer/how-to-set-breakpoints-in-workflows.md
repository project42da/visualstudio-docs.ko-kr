---
title: '워크플로 디자이너-방법: 워크플로에 중단점 설정'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: e41b21c9-c061-4358-8e2f-eb5e412864a8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d2ef863bfb899c218a65673236c284bed63aed11
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-set-breakpoints-in-workflows"></a>방법: 워크플로에 중단점 설정

Windows 워크플로 디자이너를 사용 하는 경우와 마찬가지로 Visual Basic 또는 C# 코드에서에 그래픽 워크플로의 중단점을 설정할 수 있습니다. 예상대로 설정한 각 중단점에서 워크플로 실행이 중지됩니다.

 중단점에 3 상태가: *보류 중인*, *바인딩된*, 및 *오류*합니다. 새로 설정한 중단점은 보류 중 상태가 되고 단색의 빨간색 아이콘으로 표시됩니다. 런타임 시 워크플로 형식을 로드한 경우 중단점은 바인딩됨 상태가 됩니다. 유효하지 않은 활동 이름과 같이 중단점에 대해 잘못된 형식을 지정하면 오류 창이 나타납니다. 그래도 중단점 창에 중단점이 추가되기는 하지만 소문자 "x"로 표시됩니다.

> [!NOTE]
> 호출된 워크플로에는 중단점을 설정할 수 없습니다.

> [!WARNING]
> 옵션을 선택 해야 **내 코드만 사용 (관리 전용)** 에서 **도구**, **옵션**, **디버깅** 하기 전에 메뉴 디버그 합니다. 두 시퀀스가 다른 시퀀스 내에 중첩 된 있고 첫 번째 내부 시퀀스에 중단점을 설정한 경우 키를 누르면 **F11** 경우 두 번째 내부 시퀀스를 디버깅 합니다는 **내 코드만 사용 (관리 전용)** 옵션은 해제 합니다.

> [!WARNING]
> XAML 파일 속성에 대한 전체 경로가 정확하지 않은 경우 워크플로의 중단점이 적중되지 않습니다. XAML 파일의 전체 경로는 프로젝트/솔루션을 다른 폴더 또는 다른 시스템으로 이동한 후 정확성을 잃습니다. Ctrl+S를 선택하여 전체 경로 속성을 저장하고 업데이트하세요.

## <a name="to-set-a-breakpoint-on-an-activity-in-the-design-view"></a>디자인 뷰에서 활동의 중단점을 설정하려면

1.  디버거를 중단할 활동을 선택합니다.

2.  에 **디버그** 메뉴 선택 **중단점 설정/해제**합니다. 활동의 왼쪽 위에 빨간색 아이콘이 표시됩니다.

     또는 바로 가기도 눌러 수도 **F9** 활동을 마우스 오른쪽 단추로 클릭 하 고 선택할 수 있습니다 또는 활동 선택 후 키 **중단점** 다음 **중단점 삽입**상황에 맞는 메뉴입니다.

## <a name="see-also"></a>참고자료

- [방법: 워크플로 디버거 호출](../workflow-designer/how-to-invoke-the-workflow-debugger.md)
- [워크플로 디자이너로 워크플로 디버깅](../workflow-designer/debugging-workflows-with-the-workflow-designer.md)
- [방법: 워크플로 디자이너로 XAML 디버그](../workflow-designer/how-to-debug-xaml-with-the-workflow-designer.md)