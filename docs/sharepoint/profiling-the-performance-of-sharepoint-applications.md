---
title: "SharePoint 응용 프로그램 성능 프로파일링 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.Profiling.SilverlightWebPartOnly"
  - "VS.SharePointTools.Profiling.DotNetTrustLevel"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "성능 테스트[Visual Studio에서 SharePoint 개발]"
  - "프로파일링[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 성능 테스트"
  - "Visual Studio에서 SharePoint 개발, 프로파일링"
ms.assetid: 61ae02e7-3f37-4230-bae1-54a498c2fae8
caps.latest.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# SharePoint 응용 프로그램 성능 프로파일링
  SharePoint 응용 프로그램이 느리거나 비효율적으로 수행되는 경우 Visual Studio의 프로파일링 기능을 사용하여 문제가 있는 코드 및 다른 요소를 식별할 수 있습니다.  부하 테스트 기능을 사용하면 많은 사용자가 응용 프로그램에 동시에 액세스하는 등 스트레스 상태에서 SharePoint 응용 프로그램이 어떻게 수행되는지 확인할 수 있습니다.  웹 성능 테스트를 실행하여 웹에서 응용 프로그램을 수행하는 방식을 평가할 수 있습니다.  코딩된 UI 테스트를 사용함으로써 사용자 인터페이스를 포함한 전체 SharePoint 응용 프로그램이 올바르게 작동하는지 여부를 확인할 수 있습니다.  이러한 테스트를 함께 사용하면 응용 프로그램을 배포하기 전에 성능 문제를 식별하는 데 유용합니다.  
  
## 프로파일링 도구 개요  
 프로파일링은 실행될 때 응용 프로그램의 성능 동작을 관찰하고 기록하는 프로세스를 말합니다.  응용 프로그램을 프로파일링하면 응용 프로그램이 느리게 실행되거나 너무 많은 메모리를 사용하게 하는 병목, 비효율적인 코드 및 메모리 할당 문제 같은 문제를 드러낼 수 있습니다.  예를 들어, 프로파일링을 사용하여 자주 호출되고 응용 프로그램의 전반적인 성능을 느리게 할 수 있는 코드 세그먼트인 핫 스폿을 코드에서 식별할 수 있습니다.  핫스폿을 식별한 후에는 자주 핫스폿을 최적화하거나 제거할 수 있습니다.  
  
 IDE\(통합된 개발 환경\)에서 여러 프로파일링 도구를 사용하여 이러한 유형의 성능 문제를 식별하고 찾을 수 있습니다.  이러한 도구는 다른 종류의 Visual Studio 프로젝트에서와 마찬가지로 SharePoint 프로젝트에서 동일한 방식으로 작동합니다.  프로파일링 도구 성능 마법사는 사용자가 지정하는 테스트를 사용하는 성능 세션 만들기 과정을 안내합니다.  성능 세션은 하나 이상의 프로파일링 실행 결과와 함께 응용 프로그램에서 성능 정보 수집에 사용되는 구성 데이터의 집합입니다.  성능 세션은 프로젝트 폴더에 저장되어 있으며, **성능 탐색기**에서 볼 수 있습니다.  자세한 내용은 [프로파일링 방법 이해](../profiling/understanding-performance-collection-methods.md)을 참조하십시오.  
  
 응용 프로그램에서 프로필 분석을 만들고 실행한 후에 보고서는 성능에 대한 자세한 정보를 제공합니다.  이 보고서에는 시간별 CPU 사용량 그래프, 계층 함수 호출 스택 또는 호출 트리와 같은 항목이 포함될 수 있습니다.  보고서의 정확한 내용은 샘플링 또는 계측과 같이 실행하는 테스트 형식에 따라 다를 수 있습니다.  자세한 내용은 [프로파일링 도구 보고서 개요](http://go.microsoft.com/fwlink/?LinkId=224689)를 참조하십시오.  
  
## 성능 세션 프로세스  
 응용 프로그램을 프로파일링하려면 프로파일링 도구 성능 마법사를 사용하여 성능 세션 만들기를 시작합니다.  메뉴 모음에서 **분석**, **성능 마법사 시작**을 선택합니다.  마법사가 완료되면 원하는 프로필 메서드 및 프로필하려는 응용 프로그램 같이 성능 세션에 필요한 정보를 입력합니다.  자세한 내용은 [방법: 성능 마법사를 사용하여 웹 사이트 또는 웹 응용 프로그램 프로파일링](http://go.microsoft.com/fwlink/?LinkId=224692)을 참조하십시오.  또는 명령줄 옵션을 사용하여 성능 세션을 설정하고 실행할 수 있습니다.  자세한 내용은 [명령줄에서 프로파일링 도구 사용](http://go.microsoft.com/fwlink/?LinkId=224703)을 참조하십시오.  수동으로 성능 세션의 모든 측면을 구성하려면 [방법: 프로파일링 도구를 사용하여 수동으로 성능 세션 만들기](http://go.microsoft.com/fwlink/?LinkId=224691)를 참조하십시오.  **테스트 결과** 창에서 단위 테스트에 대한 바로 가기 메뉴를 열어 **성능 세션 만들기**를 선택하여 단위 테스트에서 성능 세션을 만들 수도 있습니다.  
  
 성능 세션을 설정한 후 세션 구성이 저장되고 프로 파일링 데이터를 제공하도록 서버가 구성되며 응용 프로그램이 실행됩니다.  응용 프로그램을 사용할 때 성능 데이터는 로그 파일에 기록됩니다.  **대상** 폴더 아래 **성능 탐색기**에 성능 세션이 있습니다.  성능 세션이 완료되면 **성능 탐색기**의 **보고서** 폴더에 보고서가 나타납니다.  보고서를 표시하려면 **성능 탐색기**에서 엽니다.  성능 세션의 속성을 보거나 구성하려면 **성능 탐색기**에서 바로 가기 메뉴를 연 다음 **속성**을 선택합니다.  성능 세션의 특정 속성에 대한 자세한 내용은 [프로 파일링 도구를 위한 성능 세션 구성](http://go.microsoft.com/fwlink/?LinkId=224694)을 참조하십시오.  성능 세션의 결과를 해석하는 방법에 대한 자세한 내용은 [프로파일링 도구 데이터 분석](http://go.microsoft.com/fwlink/?LinkId=224704)을 참조하십시오.  
  
## 스트레스 테스트  
 Visual Studio Ultimate에서 부하 테스트 및 웹 성능 테스트를 만들어 응용 프로그램의 스트레스 성능을 분석할 수 있습니다.  Visual Studio에서 부하 테스트를 만들 때 응용 프로그램을 테스트할 시나리오로 불리는 요소의 조합을 지정합니다.  이러한 요소에는 부하 패턴, 테스트 조합 모델, 테스트 조합, 네트워크 조합 및 웹 브라우저 조합으로 구성됩니다.  부하 테스트 시나리오에는 단위 테스트와 웹 성능 테스트가 모두 포함될 수 있습니다.  
  
 그림 1: 부하 테스트 결과 예제  
  
 ![실행 중인 부하 테스트 그래프 뷰](../sharepoint/media/load-webgraphs.png "실행 중인 부하 테스트 그래프 뷰")  
  
 웹 성능 테스트에서는 최종 사용자가 SharePoint 응용 프로그램과 상호 작용할 수 있는 방법을 시뮬레이션합니다.  웹 성능 테스트는 브라우저 세션에서 HTTP 요청을 기록하거나 **웹 성능 테스트 레코더**를 사용하여 만들 수 있습니다.  브라우저 세션이 완료된 후  **웹 성능 테스트 편집기**에 웹 요청이 표시됩니다.  그런 다음 **웹 성능 테스트 결과 뷰어**에서 결과를 디버깅할 수 있습니다.  또한 **웹 성능 테스트 편집기**를 사용하여 웹 성능 테스트를 수동으로 빌드할 수도 있습니다.  
  
## 사용자 인터페이스 테스트  
 코딩된 UI 테스트는 UI\(사용자 인터페이스\)를 통해 SharePoint 응용 프로그램을 자동으로 구동합니다.  이러한 테스트를 통해 단추와 메뉴 등 UI 컨트롤이 제대로 작동하는지 확인합니다.  이러한 종류의 테스트는 유효성 검사 또는 다른 논리가 웹 페이지와 같은 UI에서 수행되는 경우 특히 유용합니다.  또한 코딩된 UI 테스트를 사용해서 수동 테스트를 자동화할 수도 있습니다.  다른 형식의 응용 프로그램에 대한 테스트를 만들 때와 동일한 방식으로 SharePoint 응용 프로그램에 대해 코딩된 UI 테스트를 만듭니다.  자세한 내용은 [코딩된 UI 테스트를 사용하여 SharePoint 2010 응용 프로그램 테스트](../test/testing-sharepoint-2010-applications-with-coded-ui-tests.md)을 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[Walkthrough: Profiling a SharePoint Application](../sharepoint/walkthrough-profiling-a-sharepoint-application.md)|SharePoint 응용 프로그램에서 샘플링 프로필 분석을 수행하는 방법을 보여 줍니다.|  
|[Create and run a load test](http://msdn.microsoft.com/ko-kr/7041cbcf-9ab1-4579-98ff-8f296aeaded4)|SharePoint 응용 프로그램을 스트레스 테스트하는 데 도움이 되는 부하 테스트를 만드는 방법에 대해 설명합니다.|  
|[Creating and Editing Web Performance Tests](http://msdn.microsoft.com/ko-kr/8bf5f2a7-c693-47d6-9282-5946480151dc)|사용자가 웹에서 SharePoint 사이트와 상호 작용하는 방법을 시뮬레이션해주는 웹 성능 테스트를 만드는 방법을 설명합니다.|  
|[코드 단위 테스트](../test/unit-test-your-code.md)|단위 테스트를 사용하여 코드에서 논리 오류를 찾는 방법에 대해 설명합니다.|  
|[코딩된 UI 테스트를 사용하여 SharePoint 2010 응용 프로그램 테스트](../test/testing-sharepoint-2010-applications-with-coded-ui-tests.md)|SharePoint 응용 프로그램의 사용자 인터페이스를 테스트하는 방법에 대해 설명합니다.|  
  
## 참고 항목  
 [SharePoint 솔루션 빌드 및 디버깅](../sharepoint/building-and-debugging-sharepoint-solutions.md)   
 [응용 프로그램 테스트](../Topic/Test%20apps%20early%20and%20often.md)   
 [코드 품질 향상](../test/improve-code-quality.md)  
  
  