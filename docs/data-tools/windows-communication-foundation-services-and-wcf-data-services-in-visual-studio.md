---
title: "Windows Communication Foundation 서비스 및 Visual Studio에서 WCF Data Services | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- services, WCF Data
- WCF services, binding to
- WCF services, asynchronous service methods
- service references [Visual Studio]
- WCF Data Services
- asynchronous calls
- service references [Visual Studio], type sharing
- endpoints [WCF]
- asynchronous service methods
- service references [Visual Studio] endpoints
- WCF services, type sharing
- Windows Communication Foundation, in Visual Studio
- services, WCF
- WCF service, Visual Studio
- data services, WCF
- services, in Visual Studio
- data binding [Visual Studio], WCF
- service endpoints [Visual Studio]
- service references [Visual Studio], asynchronous calls
- services, Windows Communication Foundation
- type sharing in WCF services
- WCF services, endpoints
- service method, called asynchronously[Visual Studio]
ms.assetid: d56f12cb-e139-4fec-b3e4-488383356642
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 39c9ac7b1cbed8c64ee3b87fde4c990f998157a4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="windows-communication-foundation-services-and-wcf-data-services-in-visual-studio"></a>Windows Communication Foundation 서비스 및 Visual Studio의 WCF Data Services
Visual Studio는 Windows Communication Foundation (WCF)으로 작업 하기 위한 도구를 제공 하 고 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)], 분산 응용 프로그램을 만들기 위한 Microsoft 기술입니다. 이 항목에서는에서 서비스에 대 한 소개는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 관점입니다. 전체 설명서를 참조 하십시오. [WCF 데이터 서비스 4.5](/dotnet/framework/data/wcf/index)합니다.  
  
## <a name="what-is-wcf"></a>WCF는 무엇입니까?  
 [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)]통합된 보안, 신뢰할 수 있는, 트랜잭션 및 상호 운용할 수 있는 분산된 응용 프로그램을 만들기 위한 프레임 워크가입니다. ASMX 웹 서비스,.NET Remoting, 엔터프라이즈 서비스 (DCOM) 및 MSMQ와 같은 이전 프로세스 간 통신 기술을 대체합니다. WCF 통합된 프로그래밍 모델에서 이러한 모든 기술은의 기능을 결합 합니다. 이 배포 응용 프로그램 개발 작업을 간소화 합니다.  
  
#### <a name="what-are-wcf-data-services"></a>WCF Data Services는 무엇입니까  
 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]표준 OData (개방형 데이터) 프로토콜의 구현입니다.  WCF Data Services와 같은 표준 HTTP 동사를 사용 하 여 데이터 가져오기 반환, POST, PUT 또는 DELETE 수 있도록 하는 REST Api의 집합으로 테이블 형식 데이터를 노출할 수 있습니다. 서버 쪽에서 WCF Data Services는에 의해 대체 중인 [ASP.NET Web API](http://www.asp.net/web-api) 새 OData 서비스를 만들기 위한 합니다. WCF Data Services 클라이언트 라이브러리는 Visual Studio에서.NET 응용 프로그램에서 OData 서비스를 사용 하기 위한 올바른 선택 계속 (**프로젝트 &#124; 서비스 참조 추가**). 자세한 내용은 참조 [WCF 데이터 서비스 4.5](http://go.microsoft.com/fwlink/?LinkID=119952)합니다.  
  
### <a name="wcf-programming-model"></a>WCF 프로그래밍 모델  
 두 엔터티 간의 통신을 기반으로 WCF 프로그래밍 모델은: WCF 서비스와 WCF 클라이언트입니다. 프로그래밍 모델에 캡슐화 되어는 <xref:System.ServiceModel> 네임 스페이스에는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]합니다.  
  
#### <a name="wcf-service"></a>WCF 서비스  
 WCF 서비스는 서비스와 클라이언트 간 계약을 정의 하는 인터페이스를 기반으로 합니다. 로 표시 되는 <xref:System.ServiceModel.ServiceContractAttribute> 다음 코드와 같이 특성:  
  
 [!code-csharp[WCFWalkthrough#6](../data-tools/codesnippet/CSharp/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_1.cs)]
 [!code-vb[WCFWalkthrough#6](../data-tools/codesnippet/VisualBasic/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_1.vb)]  
  
 [!code-csharp[WCFWalkthrough#1](../data-tools/codesnippet/CSharp/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_2.cs)]
 [!code-vb[WCFWalkthrough#1](../data-tools/codesnippet/VisualBasic/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_2.vb)]  
  
 함수 또는 표시 하 여 WCF 서비스에 의해 노출 되는 메서드가 정의 하는 <xref:System.ServiceModel.OperationContractAttribute> 특성입니다. 또한으로 복합 형식을 표시 하 여 serialize 된 데이터를 노출할 수 있습니다는 <xref:System.Runtime.Serialization.DataContractAttribute> 특성입니다. 이 클라이언트에서 데이터 바인딩을 활성화합니다.  
  
 인터페이스 및 해당 메서드를 정의한 후 인터페이스를 구현 하는 클래스에 캡슐화 됩니다. 단일 WCF 서비스 클래스는 여러 서비스 계약을 구현할 수 있습니다.  
  
 WCF 서비스 기능을 통해 라고에 대 한 노출 되는 *끝점*합니다. 끝점은 서비스와 통신 하는 유일한 방법은 제공 다른 클래스와 마찬가지로 직접 참조를 통해 서비스를 액세스할 수 없습니다.  
  
 끝점 주소, 바인딩 및 계약으로 구성 됩니다. 서비스가 위치한; 주소 정의 URL, FTP 주소 또는 네트워크 또는 로컬 경로 수 있습니다. 바인딩은은 서비스와 통신 하는 방식을 정의 합니다. HTTP 또는 FTP와 같은 Windows 인증 또는 사용자 이름 및 암호를 보안 메커니즘 등의 프로토콜을 지정 하기 위한 용도가 넓은 함수로 모델을 제공 하는 WCF 바인딩 등입니다. 계약에는 WCF 서비스 클래스에 의해 노출 되는 작업이 포함 됩니다.  
  
 하나의 WCF 서비스에 대 한 여러 끝점을 노출할 수 있습니다. 그러면 다른 클라이언트가 서로 다른 방법으로 동일한 서비스와 통신할 수 있습니다. 예를 들어 뱅킹 서비스 수 제공 끝점을 하나씩 직원을 위한 외부 고객에 대해 각각 다른 주소, 바인딩를 사용 하 여 및/또는 계약입니다.  
  
#### <a name="wcf-client"></a>WCF 클라이언트  
 WCF 클라이언트 구성는 *프록시* 수 있도록 하는 WCF 서비스와 통신 하는 응용 프로그램 및 서비스에 대해 정의 된 끝점과 일치 하는 끝점입니다. 프록시는 app.config 파일에서 클라이언트 쪽에서 생성 되 고 서비스에 의해 노출 되는 메서드 및 유형에 대 한 정보가 포함 됩니다. 여러 끝점을 노출 하는 서비스에 대 한 클라이언트에는 HTTP를 통해 통신 하 고 Windows 인증을 사용 하는 요구에 가장 잘 맞는 하나를 선택할 수 있습니다.  
  
 WCF 클라이언트를 만든 코드에 서비스 참조는 다른 개체와 마찬가지로. 예를 들어, 호출 하는 `GetData` 메서드 앞에 나와 다음과 유사한 코드를 작성할 수 있습니다.  
  
 [!code-csharp[WCFWalkthrough#3](../data-tools/codesnippet/CSharp/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_3.cs)]
 [!code-vb[WCFWalkthrough#3](../data-tools/codesnippet/VisualBasic/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_3.vb)]  
  
## <a name="wcf-tools-in-visual-studio"></a>Visual Studio의 WCF 도구  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]WCF 서비스와 WCF 클라이언트를 만드는 데 도움이 되는 도구를 제공 합니다. 도구를 보여 주는 연습을 참조 하십시오. [연습: Windows Forms에서 간단한 WCF 서비스 만들기](../data-tools/walkthrough-creating-a-simple-wcf-service-in-windows-forms.md)합니다.  
  
### <a name="creating-and-testing-wcf-services"></a>만들기 및 WCF 서비스를 테스트 합니다.  
 WCF를 사용할 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 템플릿을 신속 하 게 만들 사용자 고유의 서비스 기반으로 합니다. 그런 다음 디버깅 하 고 서비스를 테스트할 WCF 서비스 자동 호스트와 WCF 테스트 클라이언트를 사용할 수 있습니다. 함께 이러한 도구는 빠르고 편리한 디버그 및 테스트 주기를 제공 하 고 초기 단계에서 호스팅 모델에 대 한 커밋 할 필요가 없도록 합니다.  
  
#### <a name="wcf-templates"></a>WCF 템플릿  
 WCF [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 템플릿은 서비스 개발을 위한 기본 클래스 구조를 제공 합니다. 사용할 수 있는 몇 가지 WCF 템플릿은 **새 프로젝트 추가** 대화 상자. 여기에 WCF 서비스 라이브러리 프로젝트, WCF 서비스 웹 사이트, WCF 서비스 항목 템플릿 포함 됩니다.  
  
 서식 파일을 선택 하면 서비스 계약, 서비스 구현 및 서비스 구성에 대 한 파일이 추가 됩니다. 필요한 모든 특성이 이미 추가 되어 간단한 "Hello World" 유형의 서비스를 만들기 및 코드를 작성할 필요가 없었습니다. 함수 및 실제 서비스에 대 한 메서드를 제공 하는 코드를 추가 하려면 물론, 하지만 기본 기초를 제공 하는 서식 파일.  
  
 WCF 템플릿에 대 한 자세한 참조 [WCF Visual Studio 템플릿](/dotnet/framework/wcf/wcf-vs-templates)합니다.  
  
#### <a name="wcf-service-host"></a>WCF 서비스 호스트  
 시작 하는 경우는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] WCF 서비스 프로젝트를 호스트 하는 서비스를 로컬로 도구를 자동으로 시작 WCF 서비스 호스트에 대 한 디버거 (f5 키를 눌러). WCF 서비스 호스트 WCF 서비스 프로젝트의 서비스를 열거 하 고, 프로젝트의 구성을 로드 하 고 찾은 각 서비스에 대 한 호스트를 인스턴스화합니다.  
  
 WCF 서비스 호스트를 사용 하 여 추가 코드를 작성 하거나 개발 하는 동안 특정 호스트를 커밋하지 않고 WCF 서비스를 테스트할 수 있습니다.  
  
 WCF 서비스 호스트에 대 한 자세한 참조 [WCF 서비스 호스트 (WcfSvcHost.exe)](/dotnet/framework/wcf/wcf-service-host-wcfsvchost-exe)합니다.  
  
#### <a name="wcf-test-client"></a>WCF 테스트 클라이언트  
 WCF 테스트 클라이언트 도구 테스트 매개 변수 입력, WCF 서비스에 해당 입력 내용을 전송 수 있으며 서비스가 다시 보내는 응답을 확인 합니다. WCF 서비스 호스트와 결합 하면 테스트 환경을 편리 하 게 서비스를 제공 합니다. 이 도구는 드라이브에 설치 된 Visual Studio 2015 용 c: 여기 \Common7\IDE 폴더에서 찾을 수 있습니다: **(x86) C:\Program Files \Microsoft Visual Studio 14.0\Common7\IDE\\**합니다.  
  
 F5 키를 눌러을 WCF 서비스 프로젝트를 디버깅 하는 경우 WCF 테스트 클라이언트 열리고 구성 파일에 정의 된 서비스 끝점의 목록이 표시 됩니다. 매개 변수를 테스트 하 고 서비스를 시작 하 고 지속적으로 테스트 하 고 서비스의 유효성을 검사 하 여 해당이 프로세스를 반복 수 있습니다.  
  
 WCF 테스트 클라이언트에 대 한 자세한 참조 [WCF 테스트 클라이언트 (WcfTestClient.exe)](/dotnet/framework/wcf/wcf-test-client-wcftestclient-exe)합니다.  
  
### <a name="accessing-wcf-services-in-visual-studio"></a>Visual Studio에서 WCF 서비스에 액세스  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]WCF 클라이언트에 자동으로 생성 되는 프록시 및 사용 하 여 추가 하는 서비스에 대 한 끝점을 만드는 작업을 간소화 된 **서비스 참조 추가** 대화 상자. 모든 필요한 구성 정보는 app.config 파일에 추가 됩니다. 대부분의 경우 사용을 위해 서비스를 인스턴스화하는 수행 해야 하는 모든 합니다.  
  
 **서비스 참조 추가** 대화 상자를 사용 하는 서비스에 대 한 주소를 입력 하거나 솔루션에 정의 된 서비스를 검색할 수 있습니다. 대화 상자에는 서비스 및 해당 서비스에서 제공 하는 작업의 목록을 반환 합니다. 또한 여 코드에서 서비스 참조는 네임 스페이스를 정의할 수 있습니다.  
  
 **서비스 참조 구성** 대화 상자를 사용 하는 서비스에 대 한 구성을 사용자 지정할 수 있습니다. 서비스에 대 한 주소를 변경 하 고, 액세스 수준, 비동기 동작 및 메시지 계약 형식을 지정 하 고, 구성 형식을 다시 사용 하기 수 있습니다.  
  
## <a name="how-to-select-a-service-endpoint"></a>방법: 서비스 끝점을 선택  
일부 Windows Communication Foundation (WCF) 서비스를 통해 클라이언트가 서비스와 통신할 수 있습니다 하는 여러 끝점을 제공 합니다. 서비스 HTTP 바인딩 및 사용자 이름을 사용 하는 하나의 끝점을 노출할 수는 예를 들어 / 암호 보안 및 FTP 및 Windows 인증을 사용 하는 두 번째 끝점입니다. 반면 두 번째는 인트라넷에서 사용할 수 있습니다는 첫 번째 끝점은 방화벽 외부에서 서비스에 액세스 하는 응용 프로그램에서 사용할 수 있습니다.  
  
이 경우 지정할 수 있습니다는 `endpointConfigurationName` 서비스 참조에 대 한 생성자에 매개 변수로 합니다.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-select-a-service-endpoint"></a>서비스 끝점을 선택 하려면  
  
1.  솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 WCF 서비스에 대 한 참조를 추가 **서비스 참조 추가**합니다.
  
2.  코드 편집기에서 서비스 참조에 대 한 생성자를 추가 합니다.  
  
    ```vb  
    Dim proxy As New ServiceReference.Service1Client(  
    ```  
  
    ```csharp  
    ServiceReference.Service1Client proxy = new ServiceReference.Service1Client(  
    ```  
  
    > [!NOTE]
    >  대체 *ServiceReference* 서비스 참조 및 바꾸기에 대 한 네임 스페이스를 가진 *Service1Client* 서비스의 이름으로 합니다.  
  
3.  생성자에 대 한 오버 로드와 함께 IntelliSense 목록이 표시 됩니다. 선택 된 `endpointConfigurationName As String` 오버 로드 합니다.  
  
4.  오버 로드를 다음 입력 `=` *ConfigurationName*여기서 *ConfigurationName* 사용 하려는 끝점의 이름입니다.  
  
    > [!NOTE]
    >  사용 가능한 끝점의 이름을 모르는 경우에 app.config 파일에서 찾을 수 있습니다.  
  
#### <a name="to-find-the-available-endpoints-for-a-wcf-service"></a>WCF 서비스에 대 한 사용 가능한 끝점을 찾을 수  
  
1.  **솔루션 탐색기**서비스 참조를 포함 하는 프로젝트에 대 한 app.config 파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **열려**합니다. 파일이 코드 편집기에 표시 됩니다.  
  
2.  검색할는 `<Client>` 파일의 태그입니다.  
  
3.  아래 검색는 `<Client>` 로 시작 하는 태그에 대 한 태그 `<Endpoint>`합니다.  
  
     여러 끝점을 제공 하는 서비스 참조 될 때 발생 두 개 이상의 `<Endpoint` 태그입니다.  
  
4.  내는 `<EndPoint>` 있습니다. 태그는 `name="` *SomeService* `"` 매개 변수 (여기서 *SomeService* 끝점 이름을 나타내는). 에 전달 될 수 있는 끝점에 대 한 이름는 `endpointConfigurationName As String` 서비스 참조에 대 한 생성자의 오버 로드 합니다.  
  
## <a name="how-to-call-a-service-method-asynchronously"></a>방법: 서비스 메서드를 비동기적으로 호출  
Windows Communication Foundation (WCF) 서비스에서 대부분의 메서드는 동기적 또는 비동기적으로 호출할 수 있습니다. 메서드를 비동기적으로 호출 응용을 프로그램을 계속 느린 연결을 통해 작동 하는 경우 메서드가 호출 되는 동안 작업을 수 있습니다.  
  
기본적으로 서비스 참조를 프로젝트에 추가 되 면 메서드를 호출 동기적으로 구성 됩니다. 설정을 변경 하 여 메서드를 비동기적으로 호출 하려면 동작을 변경할 수는 **서비스 참조 구성** 대화 상자.  
  
> [!NOTE]
>  이 옵션은 각 서비스 단위로 설정 됩니다. 하나는 서비스에 대 한 메서드는 비동기적으로, 모든 메서드는 비동기적으로 호출 합니다.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-call-a-service-method-asynchronously"></a>서비스 메서드를 비동기적으로 호출 하려면  
  
1.  **솔루션 탐색기**, 서비스 참조를 선택 합니다.  
  
2.  에 **프로젝트** 메뉴를 클릭 하 여 **서비스 참조 구성**합니다.  
  
3.  에 **서비스 참조 구성** 대화 상자는 **비동기 작업 생성** 확인란 합니다.  
  
## <a name="how-to-bind-data-returned-by-a-service"></a>방법: 서비스에서 반환 된 데이터 바인딩  
컨트롤에 다른 데이터 소스를 바인딩할 수와 마찬가지로 컨트롤에는 Windows Communication Foundation (WCF) 서비스에서 반환 된 데이터를 바인딩할 수 있습니다. 서비스에 데이터를 반환 하는 복합 형식이 포함 된 경우 WCF 서비스에 참조를 추가 하면 자동으로 추가 됩니다에 **데이터 소스** 창.  
  
#### <a name="to-bind-a-control-to-single-data-field-returned-by-a-wcf-service"></a>WCF 서비스에서 반환 된 단일 데이터 필드에는 컨트롤을 바인딩하려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다. **데이터 소스** 창이 표시 됩니다.  
  
2.  에 **데이터 소스** 창에서 서비스 참조에 대 한 노드를 확장 합니다. 서비스에서 반환 되는 모든 복합 형식이 표시 됩니다.  
  
3.  형식에 대 한 노드를 확장 합니다. 해당 형식에 대 한 데이터 필드가 표시 됩니다.  
  
4.  필드를 선택 하 고 데이터 형식에 사용할 수 있는 컨트롤의 목록을 표시 하려면 드롭다운 화살표를 클릭 합니다.  
  
5.  바인딩할 원하는 컨트롤 종류를 클릭 합니다.  
  
6.  폼에 필드를 끕니다. 와 함께 폼에 컨트롤 추가 됩니다 한 <xref:System.Windows.Forms.BindingSource> 구성 요소와 <xref:System.Windows.Forms.BindingNavigator> 구성 요소입니다.  
  
7.  다른 6 있는 필드가 있지만 4 단계를 반복 바인딩할 합니다.  
  
#### <a name="to-bind-a-control-to-composite-type-returned-by-a-wcf-service"></a>WCF 서비스에서 반환 하는 복합 형식으로 컨트롤을 바인딩하려면  
  
1.  에 **데이터** 메뉴 선택 **데이터 소스 표시**합니다. **데이터 소스** 창이 표시 됩니다.  
  
2.  에 **데이터 소스** 창에서 서비스 참조에 대 한 노드를 확장 합니다. 서비스에서 반환 되는 모든 복합 형식이 표시 됩니다.  
  
3.  형식에 대 한 노드를 선택 하 고 사용할 수 있는 옵션의 목록을 표시 하려면 드롭다운 화살표를 클릭 합니다.  
  
4.  클릭 **DataGridView** 표에 데이터를 표시 하려면 또는 **세부 정보** 개별 컨트롤에 데이터를 표시 합니다.  
  
5.  노드를 폼으로 끕니다. 와 함께 폼에 컨트롤 추가 됩니다 한 <xref:System.Windows.Forms.BindingSource> 구성 요소와 <xref:System.Windows.Forms.BindingNavigator> 구성 요소입니다.  
  
## <a name="how-to-configure-a-service-to-reuse-existing-types"></a>방법: 기존 형식 다시 사용 하도록 서비스 구성  
서비스 참조를 프로젝트에 추가 되 면 서비스에 정의 된 모든 형식은 로컬 프로젝트에서 생성 됩니다. 대부분의 경우 중복 된 형식이 만들어집니다 서비스에서 사용 하는 경우 일반적인 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 형식 또는 형식 공유 라이브러리에 정의 된 경우.  
  
이 문제를 방지 하려면 참조 된 어셈블리의 형식에서에서 기본적으로 공유 됩니다. 하나 이상의 어셈블리에 대해 형식 공유를 사용 하지 않도록 설정 하려는 경우 있습니다를 수행할 수는 **서비스 참조 구성** 대화 상자.  
  
#### <a name="to-disable-type-sharing-in-a-single-assembly"></a>단일 어셈블리의 형식 공유를 사용 하지 않도록 설정 하려면  
  
1.  **솔루션 탐색기**, 서비스 참조를 선택 합니다.  
  
2.  에 **프로젝트** 메뉴를 클릭 하 여 **서비스 참조 구성**합니다.  
  
3.  에 **서비스 참조 구성** 대화 상자에서 **지정된 된 어셈블리의 형식 재사용**합니다.  
  
4.  형식 공유를 사용 하려는 각 어셈블리에 대 한 확인란을 선택 합니다. 어셈블리에 대해 형식 공유를 사용 하지 않으려면 확인란의 선택을 취소를 둡니다.  
  
#### <a name="to-disable-type-sharing-in-all-assemblies"></a>모든 어셈블리의 형식 공유를 사용 하지 않도록 설정 하려면  
  
1.  **솔루션 탐색기**, 서비스 참조를 선택 합니다.  
  
2.  에 **프로젝트** 메뉴를 클릭 하 여 **서비스 참조 구성**합니다.  
  
3.  에 **서비스 참조 구성** 대화 상자에서 지우기는 **참조 된 어셈블리의 형식 재사용** 확인란 합니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[연습: Windows Forms에서 간단한 WCF 서비스 만들기](../data-tools/walkthrough-creating-a-simple-wcf-service-in-windows-forms.md)|만들고에서 WCF 서비스를 사용 하는 단계별 데모를 보려면 제공 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.|  
|[연습: WPF 및 Entity Framework를 사용하여 WCF 데이터 서비스 만들기](../data-tools/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework.md)|만들고 사용 하는 방법의 단계별 데모를 제공 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] 에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.|  
|[WCF 개발 도구 사용](/dotnet/framework/wcf/using-the-wcf-development-tools)|만들고에서 WCF 서비스를 테스트 하는 방법에 설명 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.|  
||[방법: WCF 데이터 서비스 참조 추가, 업데이트 또는 제거](../data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference.md)|참조 하 고 사용 하는 방법을 설명 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] 에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.|  
|[서비스 참조 문제 해결](../data-tools/troubleshooting-service-references.md)|서비스 참조 및 방지 하는 방법을 사용 하 여 발생할 수 있는 몇 가지 일반적인 오류를 표시 합니다.|  
|[WCF 서비스 디버그](../debugger/debugging-wcf-services.md)|일반적인 디버깅 문제와 WCF 서비스를 디버깅할 때 발생할 수 있는 기술에 설명 합니다.|  
|[Windows Communication Foundation 인증 서비스 개요](http://msdn.microsoft.com/Library/6e121a28-89e8-4974-88a8-70aaa6a7d52b)|WCF를 사용 하 여 웹 사이트에 대 한 역할 서비스를 제공 하는 방법에 설명 합니다.|  
|[연습: N 계층 데이터 응용 프로그램 만들기](../data-tools/walkthrough-creating-an-n-tier-data-application.md)|형식화된 데이터 집합을 만들고 TableAdapter 및 데이터 집합 코드를 여러 프로젝트로 분리하는 단계별 지침을 제공합니다.|  
|[서비스 참조 구성 대화 상자](../data-tools/configure-service-reference-dialog-box.md)|사용자 인터페이스 요소에 설명 된 **서비스 참조 구성** 대화 상자.|  
  
## <a name="reference"></a>참조  
 <xref:System.ServiceModel>  
  
 <xref:System.Data.Services>  
  
## <a name="see-also"></a>참고 항목  
 [.NET용 Visual Studio 데이터 도구](../data-tools/visual-studio-data-tools-for-dotnet.md)