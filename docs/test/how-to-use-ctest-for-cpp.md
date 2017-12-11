---
title: "Visual Studio에서 CTest for C++를 사용하는 방법 | Microsoft Docs"
ms.custom: 
ms.date: 11/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8b30934-5f38-4a18-8819-263e0733cdbe
caps.latest.revision: "14"
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7e1d00460a4acf26f23c256f8eb0180360315a98
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="how-to-use-ctest-for-c-in-visual-studio"></a>Visual Studio에서 CTest for C++를 사용하는 방법 | Microsoft Docs
CMake(CTest 포함)는 **C++를 통한 데스크톱 개발** 워크로드의 구성 요소로 Visual Studio IDE에 통합되어 있습니다. 사용자의 컴퓨터에 설치하려면 Visual Studio 설치 관리자를 열고 워크로드 구성 요소 목록에서 [CMake Tools for Visual C++](/cpp/ide/cmake-tools-for-visual-cpp)를 찾습니다.

Visual Studio에서의 CMake 지원은 Visual Studio 프로젝트 시스템과 관련이 없습니다. 따라서 다른 CMake 환경에서와 마찬가지로 CTest 테스트를 작성 및 구성합니다. Visual Studio에서의 CMake 사용에 관한 자세한 내용은 [CMake Tools for Visual C++](/cpp/ide/cmake-tools-for-visual-cpp)를 참조하세요.

**Visual Studio 2017 버전 15.5** CTest는 현재 **테스트 탐색기**에 통합되지 않았습니다. CMake 주 메뉴나, **솔루션 탐색기**에서 **CMakeLists.txt** 파일의 바로 가기 메뉴에서 테스트를 실행할 수 있습니다. 테스트 결과는 Visual Studio **출력 창**으로 전달됩니다.

![CTest 테스트 실행](media/cpp-cmake-run-tests.png "CTest 테스트실행")


## <a name="see-also"></a>참고 항목
[C/C++에 대한 단위 테스트 작성](writing-unit-tests-for-c-cpp.md)


  







