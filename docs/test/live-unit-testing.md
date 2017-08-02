---
title: "Visual Studio의 Live Unit Testing | Microsoft Docs"
ms.date: 2017-03-07
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing
ms.assetid: 5b51fb96-94f4-4926-92b9-262156c05b85
author: rpetrusha
ms.author: ronpet
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: b699132bf1a31d3ef9dc3ba5af3f99c22890c632
ms.contentlocale: ko-kr
ms.lasthandoff: 05/13/2017

---

# <a name="live-unit-testing-with-visual-studio-2017"></a>Visual Studio 2017을 사용한 Live Unit Testing

응용 프로그램을 개발할 때 Live Unit Testing은 자동으로 백그라운드에서 영향을 받는 단위 테스트를 실행하고 Visual Studio IDE에서 실시간으로 결과 및 코드 검사 라이브를 표시합니다. 코드를 수정할 때 Live Unit Testing은 변경 내용이 기존 테스트에 영향을 주는 방법 및 추가한 새 코드를 하나 이상의 기존 테스트에서 검사할지 여부에 대한 피드백을 제공합니다. 그러면 버그를 수정하거나 새로운 기능을 추가할 경우에 사용자가 단위 테스트를 작성하도록 알려 줄 수 있습니다.

> [!NOTE]
> Visual Studio 2017의 엔터프라이즈 버전에서 .NET Framework를 대상으로 하는 C# 및 Visual Basic 프로젝트에 Live Unit Testing을 사용할 수 있습니다. 현재 .NET Core에서 사용할 수 없습니다.

## <a name="supported-test-frameworks"></a>지원되는 테스트 프레임워크

Live Unit Testing은 다음 테이블에 나열된 세 가지 인기 있는 단위 테스트 프레임워크를 사용합니다. 해당 어댑터와 프레임워크를 지원하는 최소 버전은 테이블에 나열됩니다. 단위 테스트 프레임워크는 NuGet.org에서 모두 사용할 수 있습니다.
 
<table> 
<tr>
   <th>테스트 프레임워크</th>
   <th>Visual Studio 어댑터 최소 버전</th>
   <th>프레임워크 최소 버전</th>
</tr>
<tr>
   <td>xUnit.net</td>
   <td> xunit.runner.visualstudio 버전 2.2.0-beta3-build1187</td>
   <td>xunit 2.0</td> 
</tr>
<tr>
   <td>NUnit</td>
   <td>NUnit3TestAdapter 버전 3.5.1</td>  
   <td>NUnit 버전 3.5.0</td>
</tr>
<tr>
   <td>MSTest</td>
   <td>MSTest.TestAdapter 1.1.4-미리 보기</td>
   <td>MSTest.TestFramework 1.0.5-미리 보기</td>
</tr>
</table>

기존 프로젝트에서 사용한 이전 어댑터 및 테스트 프레임워크 참조가 있는 경우 제거해야 합니다. (MSTest를 사용하는 경우 `Microsoft.VisualStudio.QualityTools.UnitTestFramework`에 대한 참조를 제거해야 합니다.) Live Unit Testing이 작동하지 않는 경우 새로운 항목을 추가합니다. 

경우에 따라 Live Unit Testing이 작동하기 위해 솔루션의 프로젝트에서 참조하는 NuGet 패키지를 명시적으로 복원해야 합니다. 이렇게 하려면 솔루션의 명시적 빌드를 수행합니다(최상위 Visual Studio 메뉴에서 **빌드**, **솔루션 다시 빌드**를 선택). 또는 Living Unit Testing을 활성화하기 전에 솔루션에서 패키지를 복원합니다(솔루션을 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 복원**을 선택). 

#    <a name="configuring-live-unit-testing"></a>Live Unit Testing 구성

최상위 Visual Studio 메뉴에서 **도구**, **옵션**을 선택하고 **옵션** 대화 상자의 왼쪽 창에서 **Live Unit Testing**을 선택하여 Live Unit Testing을 구성할 수 있습니다. 다음 그림에서는 대화 상자에서 사용할 수 있는 Live Unit Testing 구성 옵션을 표시합니다.

  ![이미지](~/docs/test/media/lut-options.png)

구성 가능한 옵션은 다음과 같습니다.

- 솔루션을 열면 Live Unit Testing을 자동으로 실행할지 여부
- 솔루션을 빌드 및 디버깅하거나 시스템의 배터리 전원이 지정된 임계값 미만인 경우 Live Unit Testing을 일시 중지할지 여부
- 테스트 사례의 시간이 초과되는 간격은 기본값 30초입니다. 
- Live Unit Testing에서 수행한 테스트 프로세스의 수 
- Live Unit Testing **출력** 창에 기록된 정보 수준 옵션에는 로깅되지 않음(없음), 오류 메시지만 해당(오류), 오류 및 정보 메시지(정보, 기본값) 또는 모든 세부 정보(자세한 정보 표시)가 포함됩니다.

`VS_UTE_DIAGNOSTICS`이라는 사용자 수준 환경 변수에 "1" 값을 할당하고 Visual Studio를 다시 시작하여 Live Unit Testing **출력** 창에서 자세한 정보 출력을 표시할 수도 있습니다. 

Live Unit Testing에서 파일에 자세한 MSBuild 로그 메시지를 캡처하려면 `LiveUnitTesting_BuildLog` 사용자 수준 환경 변수를 로그 포함 파일의 이름으로 설정합니다.

## <a name="starting-pausing-and-stopping-live-unit-testing"></a>Live Unit Testing 시작, 일시 중지 및 중지

최상위 Visual Studio 메뉴에서 **테스트**, **Live Unit Testing**, **시작**을 선택하여 Live Unit Testing을 활성화합니다. Live Unit Testing을 사용하면 **Live Unit Testing** 메뉴에서 사용할 수 있는 옵션이 단일 항목에서 **시작**, **일시 중지**, **중지** 및 **다시 시작**으로 변경됩니다.

언제든지 Live Unit Testing을 일시적으로 또는 완전히 중지할 수 있습니다. 예를 들어, 리팩터링하는 중에 이렇게 하려면 테스트가 한 동안 중단된다는 점을 고려하세요. 세 가지 메뉴 옵션은 다음과 같습니다.

- **일시 중지**는 Live Unit Testing을 일시적으로 중단합니다. 
    Live Unit Testing이 일시 중지되면 검사 시각화는 편집기에 표시되지 않지만 수집된 모든 데이터는 유지되었습니다. Live Unit Testing을 다시 시작하려면 Live Unit Testing 메뉴에서 "계속"을 선택합니다. Live Unit Testing은 일시 중지되는 동안 수행한 모든 편집 내용을 적용하는 데 필요한 작업을 수행하고 문자 모양을 적절하게 업데이트합니다. 
- **중지**는 Live Unit Testing을 완전히 중지합니다. Live Unit Testing은 수집된 모든 데이터를 삭제합니다.
- **다시 시작**은 **Live Unit Testing** 메뉴에서 **시작**을 선택한 다음 **중지**를 선택하는 것과 동일합니다.

##    <a name="viewing-coverage-visualization-in-the-editor-as-you-type"></a>입력할 때 편집기에서 검사 시각화 보기

Live Unit Testing은 일단 활성화되면 Visual Studio 편집기에서 코드 줄 각각을 업데이트하여 작성한 코드에 단위 테스트가 적용되는지 및 적용된 테스트에 통과하는지 여부를 표시합니다.  다음 그림에서는 테스트를 통과하거나 실패한 코드 줄뿐만 아니라 테스트가 적용되지 않은 코드 줄을 보여 줍니다. 녹색 “✓”으로 데코레이트된 줄은 테스트를 통과한 경우에만 적용됩니다. 빨간색 “🞩”으로 데코레이트된 줄은 하나 이상의 테스트에 실패한 경우 적용됩니다. 파란색 “”으로 데코레이트된 줄은 테스트되지 않은 경우에 적용됩니다.

  ![이미지](~/docs/ide/media/lut-codewindow.png)

코드 편집기에서 코드를 수정하면 즉시 Live Unit Testing 검사 시각화가 업데이트됩니다. 편집 내용을 처리하는 동안 다음 그림과 같이 통과, 실패 아래에 적용된 기호가 아닌 라운드 타이머를 추가하여 데이터가 최신 상태가 아님을 나타내도록 시각화가 변경됩니다.

  ![이미지](~/docs/test/media/lut-codeupdating.png)
 
## <a name="getting-information-on-successful-or-failed-tests"></a>성공하거나 실패한 테스트에 대한 정보 가져오기

코드 창에서 성공하거나 실패한 기호를 마우스로 가리키면 해당 줄에 도달한 테스트 수를 확인할 수 있습니다. 기호를 클릭하면 다음 그림에서처럼 개별 테스트의 상태를 볼 수 있습니다.
 
  ![이미지](~/docs/test/media/lut-failedinfo.png) 

도구 설명에서 실패한 테스트를 마우스로 가리키면 아래 이미지에 표시된 대로 확장되어 오류에 대한 추가 정보를 제공합니다. 도구 설명에서 실패한 테스트를 클릭하면 해당 테스트로 이동할 수 있습니다.

  ![이미지](~/docs/test/media/lut-failedmsg.png) 

## <a name="diagnosing-and-correcting-test-failures"></a>테스트 오류 진단 및 수정

실패한 테스트에서 제품 코드에 쉽게 디버깅하고 편집을 수행하며 응용 프로그램을 계속 개발할 수 있습니다. Live Unit Testing이 백그라운드에서 실행되므로 디버그, 편집 및 진행 주기 동안 Live Unit Testing을 다시 시작하고 중지할 필요는 없습니다.

예를 들어 이전 그림에 표시된 테스트 오류로 인해 테스트 메서드에서 알파벳이 아닌 문자가 [Char.IsLower](xref:System.Char.IsLower(System.Char)) 메서드에 전달될 때 `true`을 반환한다는 잘못된 가정을 발생시켰습니다. 테스트 메서드를 수정하면 모든 테스트를 통과합니다. 이러는 동안 Live Unit Testing을 일시 중지하거나 중지할 필요는 없습니다.

## <a name="live-unit-testing-and-test-explorer"></a>Live Unit Testing 및 Test Explorer

일반적으로 **Test Explorer**는 테스트 결과를 실행, 디버그 및 분석할 수 있게 해 주는 인터페이스를 제공합니다. Live Unit Testing은 **Test Explorer**와 통합됩니다. Live Unit Testing이 사용되지 않거나 중지되면 **Test Explorer**는 마지막으로 테스트를 실행한 단위 테스트의 상태를 표시합니다. 소스 코드를 변경하려면 테스트를 다시 실행해야 합니다. 반면에 Live Unit Testing을 사용하는 경우 **Test Explorer**에서 단위 테스트의 상태가 즉시 업데이트됩니다. 더 이상 단위 테스트를 명시적으로 실행할 필요가 없습니다. 

그러나 Live Unit Testing이 테스트 결과를 자동으로 실행하고 업데이트는 것과 **Test Explorer**에서 테스트를 명시적으로 실행하는 것은 다릅니다. 여기에는 다음이 포함됩니다.

- Test Explorer 창에서 테스트를 실행 또는 디버깅하면 일반 이진 파일을 실행합니다. 반면 Live Unit Testing은 계측된 이진 파일을 실행합니다. 
- Live Unit Testing은 테스트를 실행할 새 응용 프로그램 도메인을 만들지 않지만 기본 도메인에서 테스트를 실행합니다. **Test Explorer** 창에서 테스트를 실행하면 새 응용 프로그램 도메인을 만들지 않습니다.
- Live Unit Testing은 테스트 어셈블리 각각에서 순차적으로 테스트를 실행합니다. **Test Explorer** 창에서 여러 테스트를 실행하고 **동시에 테스트 실행** 단추를 선택한 경우 테스트가 동시에 실행됩니다.

## <a name="including-and-excluding-test-projects-and-test-methods"></a>테스트 프로젝트 및 테스트 메서드 포함 및 제외

여러 테스트 프로젝트를 포함한 솔루션에서는 Live Unit Testing에 참여하는 프로젝트 및 프로젝트의 개별 메서드를 제어할 수 있습니다. 

예를 들어 수백 개의 테스트 프로젝트를 포함한 솔루션을 구현하는 경우 Live Unit Testing에 참여할 테스트 프로젝트의 대상 집합을 선택할 수 있습니다. 단위 테스트에서 개별 프로젝트를 선택하려면 Live Unit Testing을 시작한 후에 다음을 수행합니다.

1.    Solution Explorer에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **라이브 테스트**, **제외**를 선택하여 전체 솔루션을 제외합니다.
2.    테스트에 포함하려는 테스트 프로젝트 각각을 마우스 오른쪽 단추로 클릭하고 **라이브 테스트**, **포함**을 선택합니다.
 
코드 편집기 창을 사용하여 개별 테스트 메서드를 포함하거나 제외합니다. 코드 편집기 창에서 테스트 메서드의 서명을 마우스 오른쪽 단추로 클릭하고 **라이브 테스트**, **포함** 또는 **라이브 테스트**, **제외**를 선택합니다. 

또는 [<ExcludeFromCodeCoverage>](https://msdn.microsoft.com/library/system.diagnostics.codeanalysis.excludefromcodecoverageattribute.aspx) 특성을 적용하여 Live Unit Testing에서 해당 검사를 보고하지 않도록 메서드, 클래스 또는 구조를 프로그래밍 방식으로 제외할 수 있습니다.

Live Unit Testing은 포함/제외 상태를 사용자 설정으로 저장하고 솔루션을 닫고 다시 열 경우 불러옵니다. 

## <a name="see-also"></a>참고 항목

[Live Unit Testing 블로그](https://go.microsoft.com/fwlink/?linkid=842514)   
[Live Unit Testing FAQ](live-unit-testing-faq.md)    
[채널 9 동영상: Visual Studio 2017의 Live Unit Testing](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T105)


