---
title: "Visual Studio의 코드 생성 기능 | Microsoft Docs"
ms.custom: 
ms.date: 01/11/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 7740fcea4ac944242f4284382cf26544d9ea95b5
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="code-generation-features-in-visual-studio"></a>Visual Studio의 코드 생성 기능

편집기에서 Visual Studio를 통해 코드를 생성하는 여러 가지 방법이 있습니다. 이러한 코드 생성 기능을 사용하면 시간과 키 입력을 줄이고, 구문 오류를 줄이고, 전체 코드에서 일관성을 향상시킬 수 있습니다.

코드를 생성하는 Visual Studio의 일부 기능에는 [코드 조각](../ide/code-snippets.md) 및 [빠른 작업](../ide/quick-actions.md) ![작은 전구 아이콘](media/vs2015_lightbulbsmall.png)이 포함됩니다.

[빠른 작업](../ide/quick-actions.md)을 통해 사용할 수 있는 일부 일반적인 코드 생성 작업은 다음과 같습니다.

* 클래스, 메서드, 속성 등 생성

* 추상 클래스 또는 인터페이스 구현

* 복잡한 식에 지역 변수 도입

또한 특정 문자를 입력하여 다음을 수행할 수 있습니다.

* 문서를 자동으로 생성하기 위해 나중에 처리할 수 있는 코드에 대한 [XML 형식 주석 블록]() 생성

* [메서드 재정의]() 시그니처 생성

코드 생성 논리는 언어 구문과 밀접하게 연관되어 있으므로 Visual Studio의 각 언어 서비스에서는 고유한 코드 생성 기능을 제공합니다.

## <a name="see-also"></a>참고 항목

[빠른 작업](../ide/quick-actions.md)  
[코드 조각](../ide/code-snippets.md)  
[코드 생성 및 T4 텍스트 템플릿](../modeling/code-generation-and-t4-text-templates.md)  
[리팩터링](../ide/refactoring-in-visual-studio.md)