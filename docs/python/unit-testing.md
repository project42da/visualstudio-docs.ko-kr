---
title: "Visual Studio의 Python 유닛 테스트 | Microsoft Docs"
ms.custom: 
ms.date: 7/13/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f3ad6523-5a4e-4209-8977-adc2da305df2
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: e48ebcafaca37505dbcc92bce682d0c6169004e1
ms.openlocfilehash: b68dc3d2fb7877349fc319ce5ea6e799f80c1dbf
ms.contentlocale: ko-kr
ms.lasthandoff: 07/26/2017

---

# <a name="setting-up-unit-testing-for-python-code"></a>Python 코드에 대해 단위 테스트 설정

단위 테스트는 응용 프로그램의 다른 코드 단위(일반적으로 격리된 함수, 클래스 등)를 테스트하는 코드 조각입니다. 응용 프로그램이 모든 단위 테스트를 통과하면 최소한 하위 수준 기능이 올바른 것으로 신뢰할 수 있습니다.

Python은 단위 테스트를 광범위하게 사용하여 프로그램을 설계하는 동안 시나리오를 검증합니다. Visual Studio의 Python 지원에는 테스트를 별도로 실행할 필요 없이 개발 프로세스 컨텍스트 내에서 단위 테스트 검색, 실행, 디버깅이 포함됩니다.

이 항목에서는 Visual Studio에서 Python을 사용하여 단위 테스트를 수행하는 기능에 대해 간략히 설명합니다. 일반적인 단위 테스트에 대한 자세한 내용은 [코드 단위 테스트](../test/unit-test-your-code.md)를 참조하세요.

## <a name="discovering-and-viewing-tests"></a>테스트 검색 및 보기

규칙에 따라 Visual Studio는 이름이 `test`로 시작하는 메서드로 테스트를 식별합니다. 이 동작을 확인하려면 다음을 수행합니다.

1. Visual Studio에 로드된 [Python 프로젝트](python-projects.md)를 열고 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목...**을 선택한 후 **Python 단위 테스트**, **추가**를 선택합니다.

1. 이 작업은 표준 `unittest` 모듈을 가져오고 `unittest.TestCase`에서 테스트 클래스를 파생하며 스크립트를 직접 실행하는 경우 `unittest.main()`을 호출하는 코드가 있는 `test1.py` 파일을 만듭니다.

  ```python
  import unittest

  class Test_test1(unittest.TestCase):
      def test_A(self):
          self.fail("Not implemented")

  if __name__ == '__main__':
      unittest.main()
  ```

1. 필요한 경우 파일을 저장한 다음 **테스트 > 창 > 테스트 탐색기** 메뉴 명령으로 테스트 탐색기를 엽니다.

1. 테스트 탐색기는 프로젝트에서 테스트를 검색하고 아래와 같이 표시합니다. 테스트를 두 번 클릭하면 해당 소스 파일이 열립니다.

    ![기본 test_A를 보여 주는 테스트 탐색기](media/unit-test-A.png)

1. 프로젝트에 더 많은 테스트를 추가함에 따라 도구 모음의 그룹화 방법 메뉴를 사용하여 테스트 탐색기에서 보기를 구성할 수 있습니다.

    ![테스트 탐색기 그룹화 방법 도구 모음 메뉴](media/unit-test-group-menu.png)

1. 또한 검색 필드에 텍스트를 입력하여 이름별로 테스트를 필터링할 수도 있습니다.

`unittest` 모듈 및 테스트 작성에 대한 자세한 내용은 [Python 2.7 설명서](https://docs.python.org/2/library/unittest.html) 또는 [Python 3.4 설명서](https://docs.python.org/3/library/unittest.html)(python.org)를 참조하세요.

## <a name="running-tests"></a>테스트 실행

테스트 탐색기에서 다양한 방법으로 테스트를 실행할 수 있습니다.

- **모두 실행**은 표시된 모든 테스트를 명확하게 실행합니다(필터 적용).
- **실행...**  메뉴는 실패한 테스트, 성공한 테스트 또는 실행하지 않은 테스트를 하나의 그룹으로 실행하는 명령을 제공합니다.
- 하나 이상의 테스트를 선택하고 마우스 오른쪽 단추로 클릭한 후 **선택한 테스트 실행**을 선택합니다.

백그라운드에서 테스트가 실행되고 테스트가 완료되면 테스트 탐색기에 각 테스트 상태가 업데이트됩니다.

- 성공한 테스트에는 녹색 릭과 테스트를 실행하는 데 소요된 시간이 표시됩니다.

    ![test_A 성공 상태](media/unit-test-A-pass.png)

- 실패한 테스트에는 빨간색 십자 표시와 콘솔 출력 및 테스트 실행의 `unittest` 출력을 보여 주는 **출력** 링크가 표시됩니다.

    ![test_A 실패 상태](media/unit-test-A-fail.png)

    ![test_A 실패 및 이유](media/unit-test-A-fail-reason.png)

## <a name="debugging-tests"></a>디버깅 테스트

단위 테스트는 코드 조각이므로 다른 코드처럼 버그가 있을 수 있으며 경우에 따라 디버거에서 실행해야 합니다. 디버거에서 중단점을 설정하고 변수를 검사하며 코드를 단계별로 실행할 수 있습니다. Visual Studio는 단위 테스트에 대한 진단 도구도 제공합니다.

디버깅을 시작하려면 코드에 초기 중단점을 설정한 후 테스트 탐색기에서 테스트(또는 선택)를 마우스 오른쪽 단추로 클릭하고 **선택한 테스트 디버그**를 선택합니다. 응용 프로그램 코드의 경우처럼 Visual Studio에서 Python 디버거를 시작합니다.

![테스트 디버깅](media/unit-test-debugging.png)

Visual Studio 버전에 따라 **선택한 테스트에 대한 코드 검사 분석** 및 **테스트 프로파일링** 명령도 사용할 수 있습니다([기능 매트릭스](python-in-visual-studio.md#features-matrix) 참조).

### <a name="known-issues"></a>알려진 문제

- 디버깅을 시작하면 Visual Studio에서 디버깅이 시작 및 중지되었다가 다시 시작되는 것처럼 보입니다. 이는 정상적인 동작입니다.
- 여러 테스트를 디버그하는 경우 각 테스트가 별도로 실행되므로 디버깅 세션이 중단됩니다.
- 디버깅 시 Visual Studio가 테스트를 시작하는 데 일시적으로 실패합니다. 일반적으로 테스트 디버깅을 다시 시도하면 성공합니다.
- 디버깅 시 `unittest` 구현으로 테스트에서 나갈 수 잇습니다. 일반적으로 다음 단계는 프로그램 끝까지 실행하고 디버깅을 중지합니다.
