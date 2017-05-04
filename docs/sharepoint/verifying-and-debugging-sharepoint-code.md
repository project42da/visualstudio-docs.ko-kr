---
title: "SharePoint 코드 확인 및 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "단위 테스트[Visual Studio에서 SharePoint 개발]"
  - "IntelliTrace[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, IntelliTrace"
  - "visual Studio에서 SharePoint 개발, 유닛 테스트"
ms.assetid: b5f3bce2-6a51-41b1-a292-9e384bae420c
caps.latest.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# SharePoint 코드 확인 및 디버깅
  IntelliTrace와 단위 테스트를 사용하여 SharePoint 응용 프로그램을 보다 쉽게 디버깅하고 응용 프로그램에서 각 메서드가 올바르게 작동하는지 확인할 수 있습니다.  다른 프로젝트의 형식과 동일한 절차를 수행하여 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] 에서 SharePoint 프로젝트에 이러한 기능을 사용할 수 있습니다.  
  
## IntelliTrace  
 IntelliTrace를 사용하면 SharePoint 솔루션의 현재 상태뿐만 아니라 과거에 발생한 이벤트와 해당 이벤트가 발생한 컨텍스트도 확인할 수 있습니다.  SharePoint 솔루션에서 원하는 이벤트가 기록된 다양한 시점을 앞뒤로 탐색하고 각 시점의 변수 값 및 상태를 검토할 수 있습니다.  이 동적 탐색을 사용하면 여러 중단점을 설정하지 않고도 빠르고 쉽게 SharePoint 솔루션을 디버깅할 수 있습니다.  또한 IntelliTrace 로그 \(.iTrace\) 파일에 디버깅 세션을 저장하고 나중에 Visual Studio Ultimate에서 열어 충돌 후 디버깅을 수행 할 수도 있습니다.  .iTrace 파일은 언제 어디서 특정한 SharePoint 에러가 발생했는지에 대한 자세한 정보를 포함하기 때문에 쉽게 무엇이 오류를 발생시켰는지 찾을 수 있습니다.  .iTrace 파일의 정보는 SharePoint에서 통합 로깅 시스템 \(ULS\)이 만든 전체 오류 로그의 하위 집합입니다.  이 정보는 언제 사용자 프로필이 열리거나 닫혔는지와 SharePoint 프로젝트의 속성이 언제 로드되거나 읽히거나 바뀌었는지와 같은 SharePoint에 대해 지정된 이벤트를 포함합니다.  레코드 IntelliTrace 이벤트를 구성할 수 있습니다.  자세한 내용은 [저장된 IntelliTrace 데이터 사용](../debugger/using-saved-intellitrace-data.md) 및 [디버깅 정보를 수집하도록 IntelliTrace 구성](http://msdn.microsoft.com/ko-kr/7657ecab-e07e-4b1b-872d-f05d966be37e)를 참조하십시오.  
  
 SharePoint에서 오류가 발생 하면 오류 대화 상자는 특정 오류에 대한 "correlation ID" 식별자를 표시 합니다.  .ITrace 파일에 나열된 이벤트로부터 correlation IDs를 얻을 수 있습니다.  주어진된 correlation ID를 사용 하여 발생 한 이벤트의 모든 목록을 표시 하려면 IntelliTrace 요약 페이지의 **분석** 섹션에 ID를 입력하십시오.  해당 구역에서, 발생한 이벤트의 이름만 표시할지 이벤트 이름과 함께 해당 함수 이름, 입력 및 종료 지점, 매개 변수 및 반환 값과 같은 호출 정보도 함께 표시 할지 선택 할 수 있습니다.  
  
 **F5** 키를 눌러 IntelliTrace의 Visual Studio 이벤트를 가져 올 수 있습니다.  그러나 SharePoint에 관련된 이벤트를 수집하려면 SharePoint 솔루션에서 Microsoft 모니터링 에이전트를 사용하여 IntelliTrace 데이터를 반드시 수집해야합니다.  이 도구는 IntelliTrace 데이터를 수집하고 Visual Studio 외부에서 배포된 응용 프로그램에 대한 .iTrace 파일을 만듭니다.  자세한 내용은 [IntelliTrace 기능](../debugger/intellitrace-features.md) 및 [IntelliTrace 독립 실행형 수집기 사용](../debugger/using-the-intellitrace-stand-alone-collector.md)를 참조하십시오.  
  
## 단위 테스트  
 테스트 메서드 내에 테스트 코드를 작성하고 실행할 수 있는 단위 테스트를 수행하여 코드에서 오류를 보다 쉽게 찾을 수 있습니다.  이러한 메서드에는 SharePoint 개체 모델을 기반으로 프로젝트의 논리와 기능을 확인하는 데 사용할 수 있는 빈 변수와 Assert 문이 포함되어 있습니다.  자세한 내용은 [코드 단위 테스트](../test/unit-test-your-code.md)을 참조하십시오.  
  
### Microsoft Fakes 프레임워크에 대한 지원  
 SharePoint 프로젝트는 NET Framework를 기반으로 하는 응용 프로그램에서 대리자 기반 테스트 스텁 및 shim을 만들 수 있는 격리 프레임 워크인 Microsoft Fake를 지원합니다.  Fake 프레임 워크를 사용하여 단위 테스트에 더미 구현을 만들고 유지하고 삽입할 수 있습니다.  이 스텁 및 shim 은 단위 테스트를 환경에서 격리합니다.  재정의 가능한 메서드를 사용하여 non\-sealed 클래스 또는 인터페이스를 사용하는 코드를 테스트 하기위해 스텁을 만들 수 있습니다.  하드 코드된 호출을 대체 shim 구현에 대해 정적 또는 재정의 할 수 없는 메서드를 사용하는 sealed 클래스에 리디렉션하는 shim을 만들 수 있습니다.  동적으로 개별 스텁 멤버의 동작을 사용자 지정 하기위해 스텁 형식과 shim 형식을 사용하여 대리자를 사용할 수 있습니다.  자세한 내용은 [Microsoft Fakes를 사용하여 테스트 중인 코드 격리](../test/isolating-code-under-test-with-microsoft-fakes.md)을 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[IntelliTrace 사용](../debugger/intellitrace.md)|IntelliTrace를 사용하여 Visual Studio 솔루션을 보다 쉽게 디버깅 하는 방법에 설명 합니다.|  
|[연습: IntelliTrace를 사용하여 SharePoint 응용 프로그램 디버깅](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md)|IntelliTrace를 사용하여 SharePoint 프로젝트에서 코딩 오류를 찾는 방법을 보여 줍니다.|  
|[코드 단위 테스트](../test/unit-test-your-code.md)|단위 테스트를 사용하여 코드에서 논리 오류를 찾는 방법에 대해 설명합니다.|  
  
## 참고 항목  
 [코드 품질 향상](../test/improve-code-quality.md)  
  
  