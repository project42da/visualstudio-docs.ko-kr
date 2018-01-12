---
title: "SharePoint 코드 확인 및 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- unit testing [SharePoint development in Visual Studio]
- IntelliTrace [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, IntelliTrace
- SharePoint development in Visual Studio, unit testing
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8c5eaf68a0d5349df88c2c819bce0f208721d267
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="verifying-and-debugging-sharepoint-code"></a>SharePoint 코드 확인 및 디버깅
  IntelliTrace와 유닛 테스트를 사용하여 SharePoint 솔루션을 보다 쉽게 디버깅하고 솔루션의 각 메서드가 올바르게 작동하도록 할 수 있습니다. 다른 형식의 프로젝트와 동일한 절차를 수행하여 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)]에서 SharePoint 프로젝트에 이러한 기능을 사용할 수 있습니다.  
  
## <a name="intellitrace"></a>IntelliTrace  
 IntelliTrace를 사용하면 SharePoint 솔루션의 현재 상태뿐만 아니라 과거에 발생한 이벤트와 해당 이벤트가 발생한 컨텍스트도 확인할 수 있습니다. SharePoint 솔루션에서 원하는 이벤트가 기록된 다양한 시점을 앞뒤로 탐색하고 각 시점에서 변수의 값과 상태를 검토할 수 있습니다. 이 동적 탐색을 사용하면 여러 중단점을 설정하지 않고도 보다 빠르고 쉽게 SharePoint 솔루션을 디버깅할 수 있습니다. 또한 IntelliTrace 로그(.iTrace) 파일에 디버깅 세션을 저장하고 나중에 Visual Studio Ultimate에서 열어 충돌 후 디버깅을 수행할 수도 있습니다. .ITrace 파일 오류 원인을 알아낼 보다 쉽게 수 있도록 특정 한 SharePoint 오류가 발생 시기 및 위치에 대 한 자세한 정보를 포함 합니다. .iTrace 파일의 정보는 SharePoint의 ULS(통합 로깅 시스템)가 만드는 전체 오류 로그의 하위 집합입니다. 이 정보에는 사용자 프로필이 열리거나 닫힌 시기, SharePoint 프로젝트의 속성이 로드되거나 읽히거나 변경된 시기 등의 SharePoint와 관련된 이벤트가 포함됩니다. IntelliTrace가 기록하는 이벤트를 구성할 수 있습니다. 자세한 내용은 참조 [저장 된 IntelliTrace 데이터를 사용 하 여](/visualstudio/debugger/using-saved-intellitrace-data) 및 [IntelliTrace 구성](http://msdn.microsoft.com/en-us/7657ecab-e07e-4b1b-872d-f05d966be37e)합니다.  
  
 SharePoint에서 오류가 발생하면 오류 대화 상자에 해당 특정 오류에 대한 "상관 관계 ID" 식별자가 표시됩니다. .iTrace 파일에 나열된 이벤트에서 상관 관계 ID를 가져올 수도 있습니다. 모든 지정 된 상관 관계 ID를 가진 발생 이벤트의 목록을 표시 하려면 ID에 입력할 수 있습니다는 **분석** IntelliTrace 요약 페이지의 부분입니다. 이 섹션에서 발생한 이벤트의 이름만 표시할지, 아니면 이벤트 이름과 함께 함수 이름, 종료 및 입력 지점, 매개 변수 및 반환 값과 같은 호출 정보를 표시할지를 선택할 수 있습니다.  
  
 선택 하 여 IntelliTrace에서 Visual Studio 이벤트를 가져올 수 있습니다는 **F5** 키입니다. 그러나 SharePoint와 관련된 이벤트를 가져오려면 Microsoft Monitoring Agent를 사용하여 SharePoint 솔루션에서 IntelliTrace 데이터를 수집해야 합니다. 이 도구는 IntelliTrace 데이터를 수집하고 Visual Studio 외부에서 배포된 응용 프로그램의 .iTrace 파일을 만듭니다. 자세한 내용은 참조 [IntelliTrace 기능](/visualstudio/debugger/intellitrace-features) 및 [IntelliTrace 독립 실행형 수집기를 사용 하 여](/visualstudio/debugger/using-the-intellitrace-stand-alone-collector)합니다.  
  
## <a name="unit-testing"></a>단위 테스트  
 단위 테스트를 수행 하 여 코드를 작성 하 고이 실행할 테스트 메서드 내에 테스트 코드에서 오류를 보다 쉽게 찾을 수 있습니다. 이러한 메서드에 빈 변수와 논리와 SharePoint 개체 모델을 기반으로 프로젝트의 기능을 확인 하는 데 사용할 수 있는 Assert 문이 포함 되어 있습니다. 자세한 내용은 [코드 단위 테스트](/visualstudio/test/unit-test-your-code)를 참조하세요.  
  
### <a name="support-for-microsoft-fakes-framework"></a>Microsoft Fakes 프레임워크에 대한 지원  
 SharePoint 프로젝트는 .NET Framework 기반의 응용 프로그램에서 대리자 기반 테스트 스텁 및 shim을 만들 수 있는 격리 프레임워크인 Microsoft Fake를 지원합니다. Fake 프레임워크를 사용하여 단위 테스트에서 더미 구현을 만들고, 유지 관리하고, 삽입할 수 있습니다. 이러한 스텁 및 shim은 단위 테스트를 환경에서 격리합니다. 재정의 가능한 메서드가 포함된 봉인되지 않은 클래스 또는 인터페이스를 사용하는 코드를 테스트하기 위해 스텁을 만들 수 있습니다. 정적 메서드나 재정의 가능하지 않은 메서드가 포함된 봉인된 클래스에 대한 하드 코딩된 호출을 대체 shim 구현으로 리디렉션하기 위해 shim을 만들 수 있습니다. 또한 스텁 형식 및 shim 형식이 포함된 대리자를 사용하여 개별 스텁 멤버의 동작을 동적으로 사용자 지정할 수 있습니다. 자세한 내용은 참조 [격리 코드에서 Microsoft Fakes로 테스트](/visualstudio/test/isolating-code-under-test-with-microsoft-fakes)합니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[IntelliTrace](/visualstudio/debugger/intellitrace)|IntelliTrace를 사용하여 Visual Studio 솔루션을 보다 쉽게 디버깅하는 방법을 설명합니다.|  
|[연습: IntelliTrace를 사용하여 SharePoint 응용 프로그램 디버깅](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md)|IntelliTrace를 사용하여 SharePoint 프로젝트에서 코딩 오류를 찾는 방법을 보여 줍니다.|  
|[코드 단위 테스트](/visualstudio/test/unit-test-your-code)|단위 테스트를 사용 하 여 코드에서 논리 오류를 확인 하는 방법에 설명 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [코드 품질 향상](/visualstudio/test/improve-code-quality)  
  
  