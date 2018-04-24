---
title: Visual Studio에서 부하 테스트 로그 저장 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios
- load tests, logging
ms.assetid: 9ac88d8a-4777-462c-aa0e-244dadb2cfd1
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: d5c41f358ae3990b768014a97a8b1d27420359d0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-how-frequently-test-logs-are-saved-using-the-load-test-editor"></a>방법: 부하 테스트 편집기를 사용하여 테스트 로그를 저장할 빈도 지정

**부하 테스트 새로 만들기 마법사**를 사용하여 부하 테스트를 만든 다음, **부하 테스트 편집기**를 사용하여 부하 테스트 속성을 테스트 요구 사항 및 목표에 맞게 변경할 수 있습니다. 자세한 내용은 [연습: 부하 테스트 만들기 및 실행](../test/walkthrough-create-and-run-a-load-test.md)을 참조하세요.

> [!NOTE]
> 실행 설정 속성의 전체 목록과 해당 설명을 보려면 [부하 테스트 실행 설정 속성](../test/load-test-run-settings-properties.md)을 참조하세요.

부하 테스트 편집기의 속성 창에서 **완료된 테스트에 대한 로그 빈도 저장** 속성을 변경하여 부하 테스트에서 테스트 로그가 저장되는 빈도를 지정할 수 있습니다.

## <a name="to-specify-the-frequency-for-saving-the-test-log-in-a-load-test"></a>부하 테스트에서 테스트 로그를 저장하는 빈도를 지정하려면

1.  부하 테스트를 엽니다.

     부하 테스트 편집기가 나타납니다. 부하 테스트 트리가 표시됩니다.

2.  부하 테스트 트리 **실행 설정** 폴더에서 테스트 로그가 저장되는 빈도를 지정할 실행 설정 노드를 선택합니다.

3.  **보기** 메뉴에서 **속성 창**을 선택합니다.

     시나리오의 범주와 속성이 속성 창에 표시됩니다.

4.  **완료된 테스트에 대한 로그 빈도 저장** 속성에 대한 텍스트 상자에 테스트 로그를 작성할 빈도를 나타내는 숫자를 입력합니다. 테스트 횟수가 이 숫자에 이를 때마다 테스트 로그에 테스트가 기록됩니다. 예를 들어 10을 값으로 입력하면 10번째, 20번째, 30번째 테스트 등이 테스트 로그에 기록됩니다.

    > [!NOTE]
    > **완료된 테스트에 대한 로그 빈도 저장** 속성 값을 0으로 지정하면 테스트 로그가 저장되지 않습니다.

5.  속성 변경을 마친 다음, **파일** 메뉴에서 **저장**을 선택합니다.

     로그에 저장된 데이터는 부하 테스트 분석기의 테이블 뷰를 사용하여 볼 수 있습니다. 자세한 내용은 [테이블 뷰에서 부하 테스트 결과 및 오류 분석](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [부하 테스트 시나리오 편집](../test/edit-load-test-scenarios.md)
- [연습: 부하 테스트 생성 및 실행](../test/walkthrough-create-and-run-a-load-test.md)
- [부하 테스트 시나리오 편집](../test/edit-load-test-scenarios.md)
- [방법: 테스트 실패를 테스트 로그에 저장할지 여부 지정](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)
- [방법: 가상 사용자 동작 차트를 활성화하도록 전체 정보 수집 구성](../test/how-to-configure-load-tests-to-collect-full-details.md)