---
title: Visual Studio에서 부하 테스트에 대한 카운터 집합 매핑에 컴퓨터 태그 추가 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, counter set mappings, computer tags
ms.assetid: f52a73e1-036a-4b28-a6c8-848284bf4488
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 70f3f2c58974478b17c78c3de4014a1921accd76
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-add-computer-tags-to-counter-set-mappings-using-the-load-test-editor"></a>방법: 부하 테스트 편집기를 사용하여 카운터 집합 매핑에 컴퓨터 태그 추가

컴퓨터 태그를 사용하면 구별하기 쉬운 이름으로 컴퓨터를 식별할 수 있습니다. 이 태그는 부하 테스트 편집기의 트리에 있는 **카운터 집합 매핑** 노드에 표시됩니다. 더욱 중요한 것은 이 태그가 Excel 보고서에 표시된다는 점입니다. 따라서 관련자가 부하 테스트에서 컴퓨터에 할당된 역할(예: "lab2의 Web Server1" 또는 "피닉스 사무실의 SQL Server2")을 쉽게 확인할 수 있습니다. 자세한 내용은 [테스트 비교 또는 추세 분석을 위한 부하 테스트 결과 보고](../test/compare-load-test-results.md)를 참조하세요.

## <a name="to-add-a-tag-to-a-computer"></a>컴퓨터에 태그를 추가하려면

1.  부하 테스트를 엽니다.

2.  **카운터 집합 관리** 단추를 선택합니다.

     -또는-

     부하 테스트 트리의 **카운터 집합** 폴더를 마우스 오른쪽 단추로 클릭하고 **카운터 집합 관리**를 선택합니다.

     **카운터 집합 관리** 대화 상자가 표시됩니다.

3.  (선택 사항) **선택한 컴퓨터 및 카운터 집합이 추가될 실행 설정** 목록 상자에서 다른 실행 설정을 선택합니다.

    > [!NOTE]
    > 이 내용은 부하 테스트에 실행 설정이 둘 이상 있는 경우에만 적용됩니다.

4.  **모니터링할 컴퓨터 및 카운터 집합**에서 태그를 적용할 컴퓨터를 선택합니다.

    > [!NOTE]
    > 컴퓨터를 추가하는 방법에 대한 자세한 내용은 [방법: 카운터 집합 관리](../test/how-to-manage-counter-sets-using-the-load-test-editor.md)를 참조하세요.

5.  **컴퓨터 태그**에 텍스트 상자에 컴퓨터에 연결할 태그를 입력합니다. 예를 들어 "TestMachine12 in lab3"을 입력합니다.

6.  **확인**을 선택합니다.

## <a name="see-also"></a>참고 항목

- [임계값 규칙 위반 분석](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [부하 테스트 결과 분석](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [부하 테스트에서 컴퓨터에 대한 카운터 집합 및 임계값 규칙 지정](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [방법: 카운터 집합 관리](../test/how-to-manage-counter-sets-using-the-load-test-editor.md)