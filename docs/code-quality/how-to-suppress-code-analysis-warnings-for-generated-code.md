---
title: '방법: 생성된 코드에 대한 코드 분석 경고 표시 안 함'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 29f7bdd3e29f5e45d487377f228ad965ac6e0be6
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>방법: 생성된 코드에 대한 코드 분석 경고 표시 안 함
관리 되는 코드 컴파일러는 종종 신속 하 게 코드 개발을 용이 하 게 하려면 프로젝트에 추가 되는 코드를 생성 합니다. 또한 개발자 자주 사용 하 여 타사 도구 응용 프로그램을 신속 하 게 개발할 수 있도록 지원 합니다. 또한 이러한 도구에는 프로젝트에 추가 된 코드를 생성 합니다.

 코드 분석에서 생성 된 코드에서 검색 하는 규칙 위반 보려는 수 있습니다. 그러나 보고 하 고 위반을 포함 하는 코드를 유지 관리할 수 없는 참조 하지 않을 수 있습니다.

 **생성 된 코드 결과 표시 안 함** 프로젝트의 코드 분석 속성 페이지에서 확인란을 사용 하면 타사 도구에서 생성 된 코드에서 코드 분석 경고를 표시할지 여부를 선택할 수 있습니다.

> [!NOTE]
>  이 옵션 양식 및 서식 파일에 오류 및 경고를 표시 하는 경우 생성 된 코드에서 코드 분석 오류 및 경고를 억제 하지 않습니다. 폼이나 템플릿의 소스 코드를 볼 수도 있고 유지 관리할 수도 있습니다.

### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>프로젝트에서 생성 된 코드에 대 한 경고를 표시 하지 않으려면

1.  솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 누른 **속성**합니다.

2.  클릭 **코드 분석**합니다.

3.  선택 된 **생성 된 코드 결과 표시 안 함** 확인란 합니다.