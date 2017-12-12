---
title: "Visual Studio에서 Boost.Test for C++를 사용하는 방법 | Microsoft Docs"
ms.custom: 
ms.date: 11/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0710a8-8e8a-4f6e-8415-5ab3eb830079
caps.latest.revision: "14"
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6bfce4aa4153d8f01fa9ef6cd6dc0d4b08eedbc4
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="how-to-use-boosttest-for-c-in-visual-studio"></a>Visual Studio에서 Boost.Test for C++를 사용하는 방법
**Visual Studio 2017 버전 15.5** 이상에서 Boost.Test는 **C++로 데스크톱 개발** 워크로드의 구성 요소로 Visual Studio IDE에 통합되어 있습니다. 컴퓨터에 설치하려면 Visual Studio 설치 관리자를 열고 워크로드 구성 요소 목록에서 **Boost.Test 어댑터**를 찾습니다.

![Boost Test 설치](media/cpp-boost-component.png "Boost.Test for C++ 설치")

## <a name="install-boost"></a>Boost를 설치합니다.

 Boost.Test에는 [Boost](http://www.boost.org/)가 필요합니다! Boost가 설치되어 있지 않으면 Vcpkg 패키지 관리자를 사용하는 것이 좋습니다. 

1. [Vcpkg: Windows용 C ++ 패키지 관리자](/cpp/vcpkg)의 지침에 따라 vcpkg를 설치합니다(아직 설치하지 않은 경우).
2. `vcpkg install boost`를 실행하여 Boost 라이브러리를 설치합니다.
3. `vcpkg integrate install` 명령을 실행하여 Visual Studio를 라이브러리로 구성하고 Boost 헤더와 이진 파일 경로를 포함합니다. 

## <a name="create-a-project-for-your-tests"></a>테스트용 프로젝트 만들기
Visual Studio 2017 버전 15.5에서는 미리 구성된 테스트 프로젝트 또는 항목 템플릿을 Boost.Test에 사용할 수 없습니다. 따라서 테스트를 보유할 콘솔 응용 프로그램 프로젝트를 만들어야 합니다. Boost.Test용 테스트 템플릿은 Visual Studio의 이후 버전에 포함될 예정입니다. 

1. **솔루션 탐색기**에서 솔루션 노드를 마우스 오른쪽 단추로 클릭하고 **추가 | 새 프로젝트**를 차례로 선택합니다. 
2. 왼쪽 창에서 **Windows 데스크톱**을 선택한 다음, 가운데 창에서 **Windows 콘솔 응용 프로그램**을 선택합니다. 
3. 프로젝트 이름을 지정하고 **확인**을 클릭합니다. 

## <a name="add-include-directives"></a>include 지시문 추가
.cpp 테스트 파일에서 필요한 `#include` 지시문을 추가하여 프로그램의 형식과 함수를 테스트 코드에 표시되게 합니다. 일반적으로 프로그램은 폴더 계층 구조에서 한 수준 위에 있습니다. `#include "../"`를 입력하면 IntelliSense 창이 표시되어 헤더 파일에 대한 전체 경로를 선택할 수 있습니다.

![#include 지시문 추가](media/cpp-gtest-includes.png ".cpp 테스트 파일에 include 지시문 추가")

적어도 `#include <path>/unit_test.hpp`와 함께 [Boost.Test의 단일 헤더 변형](http://www.boost.org/doc/libs/1_48_0/libs/test/doc/html/utf/user-guide/usage-variants/single-header-variant.html)을 포함시키고 `BOOST_TEST_MODULE`을 정의해야 합니다. 다음 예제는 **테스트 탐색기**에서 테스트를 검색하는 데 충분합니다.

```cpp
#include "stdafx.h"
#define BOOST_TEST_MODULE MyTest
#include <boost/test/included/unit_test.hpp>
#include "../MyProgram/MyClass.h" // project being tested
#include <string>

BOOST_AUTO_TEST_CASE(my_boost_test)
{
    std::string name = "Bill";
    MyClass mc(name);
    Assert::AreEqual();
    BOOST_CHECK(name == mc.GetName());
}
```

## <a name="write-and-run-tests"></a>테스트 작성 및 실행
이제 Boost Test를 작성하고 실행할 준비가 되었습니다. 테스트 매크로에 대한 내용은 [Boost Test 라이브러리 설명서](http://www.boost.org/doc/libs/1_38_0/libs/test/doc/html/index.html)를 참조하세요. **테스트 탐색기**를 사용한 테스트 검색, 실행 및 그룹화에 대한 내용은 [테스트 탐색기를 사용하여 단위 테스트 실행](run-unit-tests-with-test-explorer.md)을 참조하세요.

## <a name="see-also"></a>참고 항목
[C/C++에 대한 단위 테스트 작성](writing-unit-tests-for-c-cpp.md)


  







