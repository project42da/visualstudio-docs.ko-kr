---
title: Visual Studio에서 CTest for C++를 사용하는 방법 | Microsoft Docs
ms.date: 11/07/2017
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: mblome
manager: douge
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: 5956c605eb838721185598d4c5713c59164db071
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-ctest-for-c-in-visual-studio"></a>Visual Studio에서 CTest for C++를 사용하는 방법 | Microsoft Docs

CMake(CTest 포함)는 **C++를 통한 데스크톱 개발** 워크로드의 구성 요소로 기본적으로 Visual Studio IDE에 통합되어 있습니다. 사용자의 컴퓨터에 설치해야 하는 경우 Visual Studio 설치 관리자 프로그램을 열고, **수정** 단추를 클릭하고, 워크로드 구성 요소 목록에서 [Visual C++용 CMake 도구](/cpp/ide/cmake-tools-for-visual-cpp)를 선택합니다.

## <a name="to-write-tests"></a>테스트를 작성하려면

Visual Studio의 CMake 지원은 Visual Studio 프로젝트 시스템과 관련이 없습니다. 따라서 다른 CMake 환경에서와 마찬가지로 CTest 테스트를 작성 및 구성합니다. Visual Studio에서의 CMake 사용에 관한 자세한 내용은 [Visual C++용 CMake 도구](/cpp/ide/cmake-tools-for-visual-cpp)를 참조하세요.

## <a name="to-run-tests-visual-studio-2017-version-156"></a>테스트를 실행하려면(Visual Studio 2017 버전 15.6)

Visual Studio 2017 버전 15.6에서 CTest는 **테스트 탐색기**에 완전히 통합되어 있고 Google 및 Boost 유닛 테스트 프레임워크를 모두 지원합니다. 이러한 프레임워크는 기본적으로 **C++를 통한 데스크톱 개발** 워크로드의 구성 요소로 포함됩니다. 그러나 이전 버전의 Visual Studio에서 프로젝트를 업그레이드하는 경우 Visual Studio 설치 관리자 프로그램을 사용하여 해당 프레임워크를 설치해야 할 수 있습니다.

다음 그림은 Google Test 프레임워크를 사용하여 실행되는 CTest의 결과를 보여줍니다.

![VS2017 15.6에서 Google Test 프레임워크를 사용한 CTest](media/ctest-test-explorer.png "테스트 탐색기의 CTest 및 Google Test")

CTest를 사용하지만 Google 또는 Boost 어댑터를 사용하지 않는 경우 개별 테스트 메서드 수준 대신 CTest 수준에서 결과가 표시됩니다. CTest 전용 실행 파일을 디버그하고 단계별로 실행할 수 있지만 개별 테스트에 대한 스택 추적은 지원되지 않습니다.

## <a name="to-run-tests-visual-studio-2017-version-155"></a>테스트를 실행하려면(Visual Studio 2017 버전 15.5)

**Visual Studio 2017 버전 15.5**에서 CTest는 **테스트 탐색기**에 통합되어 있지 않습니다. CMake 주 메뉴나, **솔루션 탐색기**에서 **CMakeLists.txt** 파일의 바로 가기 메뉴에서 테스트를 실행할 수 있습니다. 테스트 결과는 Visual Studio **출력 창**으로 전달됩니다.

![VS2017 15.5에서 CTest 테스트 실행](media/cpp-cmake-run-tests.png "15.5에서 CTest 테스트 실행")

## <a name="see-also"></a>참고 항목

[C/C++에 대한 단위 테스트 작성](writing-unit-tests-for-c-cpp.md)