---
title: VS 셸 배포
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: e7df1991832e954def71a6cee5bd5516dfd4e961
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="vs-shell-deployment"></a>VS 셸 배포

격리 셸을 사용 하는 Visual Studio를 결정할 수 도메인 특정 언어 및 해당 솔루션이 표시 되는 방식을와 상호 작용 해야 하는 기능입니다. Visual Studio 격리 셸에 대 한 자세한 내용은 참조 [격리 셸 사용자 지정](../extensibility/customizing-the-isolated-shell.md)합니다.

## <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>Visual Studio Shell 배포 대상으로 설정 하려면

1.  에 **DslPackage** 프로젝트, 열기 **source.extension.tt**합니다.

2.  `<SupportedProducts>` 삽입:

    ```
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>
    ```

     대체 *MyIsolatedShell* 격리 셸 패키지의 이름으로 합니다.