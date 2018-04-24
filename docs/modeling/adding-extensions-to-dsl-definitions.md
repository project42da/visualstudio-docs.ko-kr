---
title: DSL 정의에 확장 추가
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 7de01ec87ca4367dcd3453c41e38c653c5184beb
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="add-extensions-to-dsl-definitions"></a>DSL 정의에 확장을 추가 합니다.

DSL 정의 확장을 사용 하면 도메인 특정 언어 (DSL)의 확장 패키지를 만들 수 있습니다. 에 VSIX Visual Studio Integration Extension ()를 포함 하는 DSL 확장과 동일한 방식으로 DSL 사용자의 컴퓨터에 설치할 수 있습니다. 추가 기능 동적으로 활성화 하 고 수 실행 시 사용할 수 없습니다. Dsl 확장을 위해 명시적으로 디자인 될 필요가 없습니다 및 확장 확장된 DSL 변경 하지 않고에 나중 또는 제 3 자가 디자인할 수 있습니다.

DSL 확장 다음과 같은 기능을 포함할 수 있습니다.

-   모델 및 프레젠테이션 요소에 대 한 속성

-   셰이프와 연결선의 데코레이터

-   클래스, 관계, 셰이프 및 연결선

-   유효성 검사 제약 조건

-   도구 상자 항목 및 탭

확장 된 DSL의 사용자를 만들고 추가 기능 인스턴스를 포함 하는 모델을 저장할 수 있습니다. 다른 사용자에 게 적절 한 확장을 설치 하 여 모델을 읽을 수 있습니다. 확장을 설치 하지 않은 사용자가 추가 기능을 사용할 수 없지만 업데이트 하 고 추가 기능을 손실 하지 않고 모델을 저장할 수 있습니다.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>참고 항목

- [관련된 블로그 게시물](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)
