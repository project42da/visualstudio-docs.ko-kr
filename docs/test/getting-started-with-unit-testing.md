---
title: "유닛 테스트 시작 - 테스트 계획 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: unit testing, create unit test plans
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: e6789c3a8ddb9b0aa317df0d2362d39946069cbd
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2018
---
# <a name="get-started-with-unit-testing"></a>유닛 테스트 시작

Visual Studio를 사용하여 코드 상태를 유지 관리하고, 코드 검사를 적용하고, 고객이 찾기 전에 오류와 결함을 찾기 위한 단위 테스트를 정의하고 실행합니다.

<a name="create-tests"></a>
## <a name="create-unit-tests"></a>단위 테스트 만들기

단위 테스트를 만들고 수시로 실행하여 코드가 올바르게 작동하는지 확인할 수 있습니다.

1. 단위 테스트 프로젝트를 만듭니다.
        
   ![솔루션에 단위 테스트 프로젝트 추가](media/createunittest1.png)
    
1. 프로젝트 이름을 지정합니다.
        
   ![단위 테스트 프로젝트 템플릿](media/createunittest2.png)
  
   프로젝트가 솔루션에 추가됩니다.
    
   ![솔루션 탐색기의 단위 테스트 프로젝트](media/createunittest5.png)
    
1. 단위 테스트 프로젝트에서 테스트하려는 프로젝트에 대한 참조를 추가합니다.
        
   ![단위 테스트 프로젝트에 참조 추가](media/createunittest6.png)
    
1. 테스트할 코드가 포함된 프로젝트를 선택합니다.
        
   ![추가할 패키지 참조 선택](media/createunittest7.png)
    
1. 단위 테스트를 코딩합니다.

   ![단위 테스트에 코드 추가](media/createunittest8.png) 

[**단위 테스트 만들기** 명령](create-unit-tests-menu.md)을 사용하여 단위 테스트 메서드 스텁을 만들 수도 있습니다.
또는 [다른 단위 테스트 프레임워크](#frameworks)를 사용하여 다른 코드 언어에 대한 테스트를 만들 수 있습니다.

![단위 테스트 만들기 명령 사용](media/createunittestcommand2.png)

## <a name="run-unit-tests"></a>단위 테스트 실행

1. 테스트 탐색기를 엽니다.
        
   ![[테스트] 메뉴에서 테스트 탐색기 열기](media/rununittest1.png) 

1. 단위 테스트를 실행합니다.
        
   ![테스트 탐색기에서 단위 테스트 실행](media/rununittest2.png) 

   테스트 탐색기에서 통과 또는 실패한 단위 테스트를 볼 수 있습니다.
      
   ![테스트 탐색기에서 단위 테스트 결과 검토](media/rununittest3.png) 

## <a name="view-live-unit-test-results"></a>라이브 단위 테스트 결과 보기

Visual Studio 2017 이상에서 MSTest, xUnit 또는 NUnit 테스트 프레임워크를 사용하고 있다면 Visual Studio UI 내에서 단위 테스트의 라이브 결과를 볼 수 있습니다.

1. **테스트** 메뉴에서 Live Unit Testing을 설정합니다.

   ![Live Unit Testing 설정](media/live-test-results-start.png) 

1. 코드를 작성하고 편집할 때 코드 편집기 창에 테스트 결과가 표시됩니다.

   ![테스트 결과 표시기를 가리키고 클릭](media/live-test-results-ui.png) 

1. 테스트 결과 표시기를 가리키고 클릭하면 추가 정보가 표시됩니다.

   ![테스트 결과 보기](media/live-test-results-details.png) 

자세한 내용은 [Live Unit Testing in Visual Studio](https://blogs.msdn.microsoft.com/visualstudio/2016/11/18/live-unit-testing-visual-studio-2017-rc/)(Visual Studio의 Live Unit Testing)를 참조하세요.

<a name="intellitest"></a>
## <a name="generate-unit-tests-with-intellitest"></a>IntelliTest를 사용하여 단위 테스트 생성

IntelliTest를 실행하면 오류가 발생하는 테스트를 쉽게 확인하고 필요한 코드를 추가하여 수정할 수 있습니다. 생성된 테스트 중에서 재발 테스트 모음을 제공하기 위해 테스트 프로젝트에 저장할 테스트를 선택할 수 있습니다. 코드를 변경하면 IntelliTest를 다시 실행하여 생성된 테스트를 코드 변경 내용과 동기화합니다. 방법을 알아보려면 [IntelliTest를 사용하여 코드에 대한 단위 테스트 생성](../test/generate-unit-tests-for-your-code-with-intellitest.md)을 참조하세요.

![IntelliTest를 사용하여 단위 테스트 생성](media/intellitest.png)

<a name="unit-tests"></a>
## <a name="run-unit-tests-with-test-explorer"></a>테스트 탐색기를 사용하여 단위 테스트 실행

테스트 탐색기를 사용하여 Visual Studio 또는 타사 단위 테스트 프로젝트에서 단위 테스트를 실행하고, 테스트를 범주로 그룹화하며, 테스트 목록을 필터링하고, 테스트 PLAYLIST를 만들어 저장하고 실행할 수 있습니다. 테스트를 디버그하고 테스트 성능 및 코드 검사를 분석할 수도 있습니다. 방법을 알아보려면 [테스트 탐색기를 사용하여 단위 테스트 실행](../test/run-unit-tests-with-test-explorer.md)을 참조하세요.

![테스트 탐색기를 사용하여 단위 테스트 실행](media/testexplorer.png)

<a name="code-coverage"></a>
## <a name="use-code-coverage-to-determine-how-much-code-is-being-tested"></a>코드 검사를 사용하여 테스트할 코드 범위 결정

프로젝트의 코드 중 유닛 테스트와 같은 코딩된 테스트를 사용하여 실제로 테스트할 부분을 결정하려면 Visual Studio의 코드 검사 기능을 사용합니다. 버그로부터 효과적으로 보호하려면 코드의 상당한 부분을 실행 또는 '검사'해야 합니다. 방법을 알아보려면 [코드 검사를 사용하여 테스트할 코드 범위 결정](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)을 참조하세요.

![코드 검사를 사용하여 테스트할 코드 범위 결정](media/codecoverage.png)

## <a name="q--a"></a>Q&A

<!-- BEGINSECTION class="m-qanda" -->

<a name="frameworks">

</a>
####Q: 다른 단위 테스트 프레임워크를 사용하는 경우에 Visual Studio에서 단위 테스트를 실행할 수 있나요?

A: Visual Studio의 Test Runner가 해당 프레임워크와 함께 작동할 수 있도록 해당 프레임워크용 플러그 인을 사용하세요. 여기에서 Visual Studio용 [유닛 테스트 프레임워크 플러그 인](http://go.microsoft.com/fwlink/?LinkID=246630)을 지금 바로 사용할 수 있습니다.

1. Visual Studio의 확장 관리자를 사용하여 플러그 인을 다운로드합니다.
        
   ![확장 관리자를 사용하여 타사 단위 테스트 플러그 인 선택](media/install3rdpartyunittestframeworks1.png) 

1. Visual Studio 갤러리의 도구/테스트에서 플러그 인을 다운로드하거나 이름을 아는 경우 검색합니다.
        
   ![플러그 인 다운로드](media/install3rdpartyunittestframeworks2.png) 

1. 클래스 라이브러리 프로젝트를 만듭니다.
        
   ![클래스 라이브러리 프로젝트 만들기](media/create3rdpartyunittest1.png) 

   솔루션에 프로젝트를 추가합니다.
    
   ![클래스 라이브러리 프로젝트 이름 지정 및 추가](media/create3rdpartyunittest3.png) 

1. 클래스 라이브러리 프로젝트에서 NuGet를 실행하여 플러그 인을 설치합니다.

   ![NuGet 패키지를 관리하여 플러그 인 설치](media/create3rdpartyunittest3a.png) 

   [NuGet](https://www.nuget.org/)은 Visual Studio의 확장 프로그램으로, 프로젝트의 라이브러리 및 도구를 추가하고 업데이트하는 데 사용할 수 있습니다.

1. 플러그 인을 설치합니다. 이름을 아는 경우 온라인으로 검색할 수 있습니다.

   ![타사 프레임워크 설치](media/create3rdpartyunittest4.png) 

   프레임워크가 프로젝트에서 참조됩니다.
        
   ![타사 단위 테스트 프레임워크에 대한 참조가 솔루션에 추가됨](media/create3rdpartyunittest6.png) 

1. 클래스 라이브러리 프로젝트에서 테스트하려는 프로젝트에 대한 참조를 추가합니다.
        
   ![프로젝트에 참조 추가](media/createunittest6.png) 

1. 테스트할 코드가 포함된 프로젝트를 선택합니다.
        
   ![테스트할 코드 프로젝트 선택](media/createunittest7.png) 

1. 단위 테스트를 코딩합니다.

   ![단위 테스트에 코드 추가](media/create3rdpartyunittest7.png)   

<!-- ENDSECTION -->

## <a name="see-also"></a>참고 항목

* [단위 테스트 만들기 명령](create-unit-tests-menu.md)
* [IntelliTest를 사용하여 테스트 생성](generate-unit-tests-for-your-code-with-intellitest.md)
* [테스트 탐색기를 사용하여 테스트 실행](run-unit-tests-with-test-explorer.md)
* [코드 검사 결정](using-code-coverage-to-determine-how-much-code-is-being-tested.md)
* [코드 품질 향상](improve-code-quality.md)
