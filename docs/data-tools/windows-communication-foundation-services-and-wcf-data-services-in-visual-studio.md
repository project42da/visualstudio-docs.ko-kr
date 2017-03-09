---
title: "Windows Communication Foundation Services and WCF Data Services in Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "services, WCF Data"
  - "WCF services, binding to"
  - "WCF services, asynchronous service methods"
  - "service references [Visual Studio]"
  - "WCF Data Services"
  - "asynchronous calls"
  - "service references [Visual Studio], type sharing"
  - "endpoints [WCF]"
  - "asynchronous service methods"
  - "service references [Visual Studio] endpoints"
  - "WCF services, type sharing"
  - "Windows Communication Foundation, in Visual Studio"
  - "services, WCF"
  - "WCF service, Visual Studio"
  - "data services, WCF"
  - "services, in Visual Studio"
  - "data binding [Visual Studio], WCF"
  - "service endpoints [Visual Studio]"
  - "service references [Visual Studio], asynchronous calls"
  - "services, Windows Communication Foundation"
  - "type sharing in WCF services"
  - "WCF services, endpoints"
  - "service method, called asynchronously[Visual Studio]"
ms.assetid: d56f12cb-e139-4fec-b3e4-488383356642
caps.latest.revision: 26
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Communication Foundation Services and WCF Data Services in Visual Studio
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 2008에서는 분산 응용 프로그램을 작성하기 위한 Microsoft 기술인 WCF\(Windows Communication Foundation\) 및 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]를 사용하는 데 필요한 도구를 제공합니다.  이 항목에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 측면에서 서비스를 소개합니다.  
  
## WCF의 정의  
 [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)]는 안전하고 신뢰할 수 있으며, 트랜잭션 및 상호 운용이 가능한 분산 응용 프로그램을 만들기 위한 통합 프레임워크입니다.  이전 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에는 응용 프로그램 간의 통신을 위해 여러 가지 기술들이 사용되었습니다.  
  
 예를 들어 모든 플랫폼에서 액세스할 수 있는 방식으로 정보를 공유하려는 경우에는 ASMX 웹 서비스라고도 하는 웹 서비스가 사용되었으며,  Windows 운영 체제에서 실행되는 클라이언트와 서버 사이에 데이터를 이동하는 작업만 필요한 경우에는 .NET Remoting이 사용되었습니다.  또한 트랜잭션 통신이 필요한 경우를 위한 엔터프라이즈 서비스\(DCOM\)나 큐 대기 모델에 필요한 메시지 큐\(MSMQ라고도 함\)도 사용되었습니다.  
  
 WCF는 이러한 모든 기술의 기능을 하나의 통합된 프로그래밍 모델에 결합하여  분산 응용 프로그램 개발 작업을 간단하게 만듭니다.  
  
#### WCF Data Services의 정의  
 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]는 데이터베이스와 직접 상호 작용하여 GET, POST, PUT, DELETE 등과 같은 표준 HTTP 동사를 사용하여 데이터를 반환할 수 있는 서비스입니다.  일반적으로 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]는 데이터베이스에서 레코드를 만들거나 업데이트 또는 삭제하는 데 사용되는 응용 프로그램에 적합합니다.  자세한 내용은 [ADO.NET Data Services Framework](http://go.microsoft.com/fwlink/?LinkID=119952)를 참조하십시오.  
  
### WCF 프로그래밍 모델  
 WCF 프로그래밍 모델은 WCF 서비스와 WCF 클라이언트라는 두 엔터티 사이의 통신을 기반으로 합니다.  이 프로그래밍 모델은 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 <xref:System.ServiceModel> 네임스페이스에 캡슐화됩니다.  
  
#### WCF 서비스  
 WCF 서비스는 서비스와 클라이언트 사이의 계약을 정의하는 인터페이스를 기반으로 하며  다음 코드와 같이 <xref:System.ServiceModel.ServiceContractAttribute> 특성으로 표시됩니다.  
  
 [!code-cs[WCFWalkthrough#6](../data-tools/codesnippet/CSharp/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_1.cs)]
 [!code-vb[WCFWalkthrough#6](../data-tools/codesnippet/VisualBasic/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_1.vb)]  
  
 [!code-cs[WCFWalkthrough#1](../data-tools/codesnippet/CSharp/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_2.cs)]
 [!code-vb[WCFWalkthrough#1](../data-tools/codesnippet/VisualBasic/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_2.vb)]  
  
 WCF 서비스에서 노출하는 함수나 메서드는 <xref:System.ServiceModel.OperationContractAttribute> 특성을 표시하여 정의합니다.  또한 복합 형식에 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 표시하여 serialize된 데이터를 노출할 수 있습니다.  이렇게 하면 클라이언트에서 데이터 바인딩을 수행할 수 있습니다.  
  
 정의된 인터페이스와 해당 메서드는 인터페이스를 구현하는 클래스에 캡슐화됩니다.  단일 WCF 서비스 클래스는 여러 서비스 계약을 구현할 수 있습니다.  
  
 WCF 서비스는 클라이언트에서 사용할 수 있도록 *끝점*을 통해 노출됩니다.  WCF 서비스와의 통신은 끝점을 통해서만 가능하며 다른 클래스를 사용할 때처럼 직접 참조를 통해 서비스에 액세스할 수 없습니다.  
  
 끝점은 주소, 바인딩 및 계약으로 구성됩니다.  주소는 서비스의 위치에 대한 정의로 URL, FTP 주소 또는 네트워크나 로컬 경로 등으로 정의될 수 있습니다.  바인딩은 서비스와 통신하는 방법을 정의합니다.  WCF 바인딩은 HTTP나 FTP 같은 프로토콜, Windows 인증이나 사용자 이름과 암호 같은 보안 메커니즘 등을 지정할 수 있는 다양한 기능의 모델을 제공합니다.  계약에는 WCF 서비스 클래스에서 노출하는 작업이 포함됩니다.  
  
 WCF 서비스 하나에 대해 끝점을 여러 개 노출할 수 있습니다.  이렇게 하면 여러 클라이언트에서 서로 다른 방식으로 동일한 서비스와 통신할 수 있습니다.  예를 들어 뱅킹 서비스의 경우 서로 다른 주소, 바인딩 및\/또는 계약을 사용하여 직원을 위한 끝점과 외부 고객을 위한 끝점을 각각 제공할 수 있습니다.  
  
#### WCF 클라이언트  
 WCF 클라이언트는 응용 프로그램에서 WCF 서비스와의 통신할 수 있도록 하는 *프록시* 및 서비스에 대해 정의된 끝점과 일치하는 끝점으로 구성됩니다.  프록시는 클라이언트 쪽의 app.config 파일에 생성되며, 서비스에서 노출하는 형식과 메서드에 대한 정보를 포함합니다.  서비스가 끝점을 여러 개 노출하는 경우 클라이언트에서는 요구 사항에 가장 적합한 끝점을 선택할 수 있습니다. 예를 들어 HTTP를 통해 통신하면서 Windows 인증 방식을 사용할 수도 있습니다.  
  
 WCF 클라이언트를 만든 후에는 다른 개체를 참조할 때와 마찬가지로 코드에서 서비스를 참조합니다.  예를 들어 앞에서 설명한 `GetData` 메서드를 호출하려면 코드를 다음과 같이 작성합니다.  
  
 [!code-cs[WCFWalkthrough#3](../data-tools/codesnippet/CSharp/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_3.cs)]
 [!code-vb[WCFWalkthrough#3](../data-tools/codesnippet/VisualBasic/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_3.vb)]  
  
## Visual Studio의 WCF 도구  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 2008에서는 WCF 서비스와 WCF 클라이언트를 모두 만드는 데 도움을 주는 도구를 제공합니다.  이러한 도구를 보여 주는 연습은 [Walkthrough: Creating and Accessing WCF Services](../data-tools/walkthrough-creating-a-simple-wcf-service-in-windows-forms.md)을 참조하십시오.  
  
### WCF 서비스 만들기 및 테스트  
 WCF [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 템플릿을 토대로 고유한 서비스를 빠르게 만들 수 있습니다.  그런 다음 WCF 서비스 자동 호스트 및 WCF 테스트 클라이언트를 사용하여 서비스를 디버깅하고 테스트할 수 있습니다.  이러한 도구를 사용하면 빠르고 편리하게 디버깅 및 테스팅 과정을 진행할 수 있으며 초기 단계에서 호스팅 모델에 커밋하지 않아도 됩니다.  
  
#### WCF 템플릿  
 WCF [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 템플릿은 서비스 개발을 위한 기본 클래스 구조를 제공합니다.  **새 프로젝트 추가** 대화 상자에는  WCF 서비스 라이브러리 프로젝트, WCF 서비스 웹 사이트, WCF 서비스 항목 템플릿 같은 여러 가지 템플릿이 있습니다.  
  
 템플릿을 선택하면 서비스 계약, 서비스 구현 및 서비스 구성에 필요한 파일이 추가됩니다.  필요한 모든 특성이 이미 추가되어 있어서 간단한 "Hello World" 형식의 서비스 정도는 코드를 직접 작성하지 않고도 만들 수 있습니다.  실제 서비스에 필요한 함수와 메서드를 제공하는 코드는 직접 작성해야 하지만 기본적인 틀은 템플릿에서 제공합니다.  
  
 WCF 템플릿에 대한 자세한 내용은 [WCF Visual Studio 템플릿](../Topic/WCF%20Visual%20Studio%20Templates.md)을 참조하십시오.  
  
#### WCF 서비스 호스트  
 F5 키를 눌러 WCF 서비스 프로젝트에 대해 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디버거를 시작하면 WCF 서비스 호스트 도구가 자동으로 시작되어 서비스를 로컬로 호스팅합니다.  WCF 서비스 호스트는 WCF 서비스 프로젝트의 서비스를 열거하고, 프로젝트의 구성을 로드하고, 검색되는 각 서비스에 대해 호스트를 인스턴스화합니다.  
  
 WCF 서비스 호스트를 사용하면 코드를 추가로 작성하거나 개발 단계에서 특정 호스트에 커밋하지 않고 WCF 서비스를 테스트할 수 있습니다.  
  
 WCF 서비스 호스트에 대한 자세한 내용은 [WCF 서비스 호스트\(WcfSvcHost.exe\)](../Topic/WCF%20Service%20Host%20\(WcfSvcHost.exe\).md)를 참조하십시오.  
  
#### WCF 테스트 클라이언트  
 WCF 테스트 클라이언트 도구를 사용하면 테스트 매개 변수를 입력한 후 해당 입력 내용을 WCF 서비스에 제출하여 서비스에서 보내는 응답을 볼 수 있습니다.  이 도구를 WCF 서비스 호스트와 함께 사용하면 서비스 테스트 작업을 편리하게 수행할 수 있습니다.  
  
 F5 키를 눌러 WCF 서비스 프로젝트 디버깅을 시작하면 WCF 테스트 클라이언트가 열리고 구성 파일에 정의되어 있는 서비스 끝점 목록이 표시됩니다.  매개 변수를 테스트하고 서비스를 시작할 수 있으며 이 프로세스를 계속 반복하여 서비스를 지속적으로 테스트하고 유효성을 검사할 수 있습니다.  
  
 WCF 테스트 클라이언트에 대한 자세한 내용은 [WCF 테스트 클라이언트\(WcfTestClient.exe\)](../Topic/WCF%20Test%20Client%20\(WcfTestClient.exe\).md)를 참조하십시오.  
  
### Visual Studio에서 WCF 서비스에 액세스  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]프록시 및 끝점을 사용 하 여 추가 서비스에 대해 자동으로 생성 하는 WCF 클라이언트를 만드는 작업을 단순화할 수 있는  **서비스 참조 추가** 대화 상자.  필요한 모든 구성 정보는 app.config 파일에 자동으로 추가됩니다. 따라서 대부분의 경우 사용자는 사용할 서비스를 인스턴스화하기만 하면 됩니다.  
  
 **서비스 참조 추가** 대화 상자를 사용하면 서비스의 주소를 입력하거나, 솔루션에 정의되어 있는 서비스를 검색할 수 있습니다.  이 대화 상자에서는 서비스 목록 및 해당 서비스에서 제공하는 작업을 반환합니다.  또한 이 대화 상자를 사용하면 코드에서 서비스를 참조하는 데 사용할 네임스페이스를 정의할 수도 있습니다.  
  
 **서비스 참조 구성** 대화 상자를 사용하면 서비스의 구성을 사용자 지정할 수 있습니다.  예를 들어 서비스의 주소를 변경하거나 액세스 수준, 비동기 동작 및 메시지 계약 형식을 지정하거나, 형식 재사용을 구성할 수 있습니다.  
  
## 방법: 서비스 끝점 선택  
 일부 WCF\(Windows Communication Foundation\) 서비스는 클라이언트가 서비스와 통신하는 데 사용할 수 있는 여러 끝점을 노출합니다.  예를 들어 서비스에서 HTTP 바인딩 및 사용자 이름\/암호 보안을 사용하는 끝점과 FTP 및 Windows 인증을 사용하는 두 번째 끝점이 사용될 수 있습니다.  첫 번째 끝점은 방화벽 외부에서 서비스에 액세스하는 응용 프로그램이 사용할 수 있는 반면 두 번째 끝점은 인트라넷에서 사용될 수 있습니다.  
  
 이 경우 `endpointConfigurationName`을 서비스 참조의 생성자에 대한 매개 변수로 지정할 수 있습니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### 서비스 끝점을 선택하려면  
  
1.  WCF 서비스에 참조를 추가합니다.  자세한 내용은 [How to: Add, Update, or Remove a Service Reference](../Topic/How%20to:%20Add,%20Update,%20or%20Remove%20a%20Service%20Reference.md)를 참조하십시오.  
  
2.  코드 편집기에서 서비스 참조의 생성자를 추가합니다.  
  
    ```vb#  
    Dim proxy As New ServiceReference.Service1Client(  
    ```  
  
    ```c#  
    ServiceReference.Service1Client proxy = new ServiceReference.Service1Client(  
    ```  
  
    > [!NOTE]
    >  *ServiceReference*를 서비스 참조의 네임스페이스로 바꾸고 *Service1Client*를 서비스 이름으로 바꿉니다.  
  
3.  생성자의 오버로드를 포함하는 IntelliSense 목록이 표시됩니다.  `endpointConfigurationName As String` 오버로드를 선택합니다.  
  
4.  오버로드 다음에 `=` *ConfigurationName*을 입력합니다. 여기서 *ConfigurationName*은 사용할 끝점의 이름입니다.  
  
    > [!NOTE]
    >  사용 가능한 끝점의 이름을 모르는 경우 app.config 파일에서 찾을 수 있습니다.  
  
#### WCF 서비스에 사용 가능한 끝점을 찾으려면  
  
1.  **솔루션 탐색기**에서 서비스 참조를 포함하는 프로젝트의 app.config 파일을 마우스 오른쪽 단추로 클릭한 다음 **열기**를 클릭합니다.  파일이 코드 편집기에 나타납니다.  
  
2.  파일에서 `<Client>` 태그를 검색합니다.  
  
3.  `<Client>` 태그 아래에서 `<Endpoint>`로 시작하는 태그를 검색합니다.  
  
     서비스 참조가 여러 끝점을 제공하는 경우 둘 이상의 `<Endpoint` 태그가 있습니다.  
  
4.  `<EndPoint>` 태그 내부에 `name="`*SomeService*`"` 매개 변수가 있습니다. 여기서 *SomeService*는 끝점 이름을 나타냅니다.  이 이름은 서비스 참조에 대해 생성자의 `endpointConfigurationName As String` 오버로드로 전달될 수 있는 끝점의 이름입니다.  
  
## 방법: 비동기적으로 서비스 메서드 호출  
 WCF\(Windows Communication Foundation\) 서비스의 메서드 대부분은 동기적 또는 비동기적으로 호출할 수 있습니다.  메서드를 비동기적으로 호출하면 저속 연결을 통해 작업하는 경우 메서드를 호출하는 동안 응용 프로그램 작업을 계속할 수 있습니다.  
  
 기본적으로 프로젝트에 추가하는 서비스 참조는 메서드를 동기적으로 호출하도록 구성됩니다.  필요한 경우 **서비스 참조 구성** 대화 상자에서 설정을 변경하여 메서드를 비동기적으로 호출하도록 동작을 변경할 수 있습니다.  
  
> [!NOTE]
>  이 옵션은 각 서비스별로 설정됩니다.  따라서 서비스의 특정 메서드를 비동기적으로 호출하면 모든 메서드를 비동기적으로 호출해야 합니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### 서비스 메서드를 비동기적으로 호출하려면  
  
1.  **솔루션 탐색기**에서 서비스 참조를 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **서비스 참조 구성**을 클릭합니다.  
  
3.  **서비스 참조 구성** 대화 상자에서 **비동기 작업 생성** 확인란을 선택합니다.  
  
## 방법: 서비스에서 반환 된 데이터 바인딩  
 컨트롤에 다른 데이터 소스를 바인딩할 수 있는 것과 마찬가지로 WCF\(Windows Communication Foundation\) 서비스에서 반환된 데이터도 컨트롤에 바인딩할 수 있습니다.  WCF 서비스에 대한 참조를 추가할 경우 데이터를 반환하는 복합 형식이 서비스에 포함되어 있으면 해당 형식이 **데이터 소스** 창에 자동으로 추가됩니다.  
  
#### WCF 서비스에서 반환된 단일 데이터 필드에 컨트롤을 바인딩하려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  **데이터 소스** 창이 나타납니다.  
  
2.  **데이터 소스** 창에서 서비스 참조 노드를 확장합니다.  서비스에서 반환되는 모든 복합 형식이 표시됩니다.  
  
3.  특정 형식의 노드를 확장합니다.  해당 형식의 데이터 필드가 표시됩니다.  
  
4.  필드를 선택하고 드롭다운 화살표를 클릭하여 해당 데이터 형식에 사용할 수 있는 컨트롤 목록을 표시합니다.  
  
5.  바인딩할 컨트롤 형식을 클릭합니다.  
  
6.  필드를 폼에 끌어 옵니다.  그러면 컨트롤이 <xref:System.Windows.Forms.BindingSource> 구성 요소 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소와 함께 폼에 추가됩니다.  
  
7.  바인딩할 다른 모든 필드에 대해 4\-6단계를 반복합니다.  
  
#### WCF 서비스에서 반환된 복합 형식에 컨트롤을 바인딩하려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 선택합니다.  **데이터 소스** 창이 나타납니다.  
  
2.  **데이터 소스** 창에서 서비스 참조 노드를 확장합니다.  서비스에서 반환되는 모든 복합 형식이 표시됩니다.  
  
3.  특정 형식의 노드를 선택하고 드롭다운 화살표를 클릭하여 사용 가능한 옵션 목록을 표시합니다.  
  
4.  **DataGridView**를 클릭하여 데이터를 표에 표시하거나 **자세히**를 클릭하여 데이터를 개별 컨트롤에 표시합니다.  
  
5.  노드를 폼으로 끌어 옵니다.  그러면 컨트롤이 <xref:System.Windows.Forms.BindingSource> 구성 요소 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소와 함께 폼에 추가됩니다.  
  
## 방법: 기존 형식을 재사용 하도록 서비스를 구성 합니다.  
 프로젝트에 서비스 참조를 추가하면 서비스에 정의되어 있는 모든 형식이 로컬 프로젝트에 생성됩니다.  대부분의 경우 서비스가 공용 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 형식을 사용하거나 형식이 공유 라이브러리에 정의되어 있으면 중복된 형식이 만들어집니다.  
  
 이 문제를 방지하기 위해 참조된 어셈블리의 형식은 기본적으로 공유됩니다.  어셈블리 하나 이상에서 형식을 공유하지 않도록 설정하려면 **서비스 참조 구성** 대화 상자에서 설정을 변경할 수 있습니다.  
  
#### 단일 어셈블리에서 형식 공유를 해제하려면  
  
1.  **솔루션 탐색기**에서 서비스 참조를 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **서비스 참조 구성**을 클릭합니다.  
  
3.  **서비스 참조 구성** 대화 상자에서 **참조된 어셈블리 중 지정된 어셈블리의 형식 재사용**을 선택합니다.  
  
4.  형식을 공유할 각 어셈블리의 확인란을 선택합니다.  형식을 공유하지 않을 어셈블리의 확인란은 선택하지 않은 상태로 둡니다.  
  
#### 모든 어셈블리에서 형식 공유를 해제하려면  
  
1.  **솔루션 탐색기**에서 서비스 참조를 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **서비스 참조 구성**을 클릭합니다.  
  
3.  **서비스 참조 구성** 대화 상자에서 **참조된 어셈블리의 형식 재사용** 확인란의 선택을 취소합니다.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[Walkthrough: Creating and Accessing WCF Services](../data-tools/walkthrough-creating-a-simple-wcf-service-in-windows-forms.md)|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 WCF 서비스를 만들고 사용하는 방법을 단계별로 보여 줍니다.|  
|[Walkthrough: Creating and Accessing a WCF Data Service in Visual Studio](../data-tools/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework.md)|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]를 만들고 사용하는 방법을 단계별로 보여 줍니다.|  
|[WCF 개발 도구 사용](../Topic/Using%20the%20WCF%20Development%20Tools.md)|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 WCF 서비스를 만들고 테스트하는 방법을 설명합니다.|  
|[How to: Add, Update, or Remove a Service Reference](../Topic/How%20to:%20Add,%20Update,%20or%20Remove%20a%20Service%20Reference.md)|프로젝트에서 WCF 서비스를 추가, 업데이트 또는 제거하는 방법을 설명합니다.|  
|[How to: Add, Update, or Remove a WCF Data Service Reference](../data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference.md)|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]를 참조하고 사용하는 방법을 설명합니다.|  
|[How to: Add a Reference to a Web Service](../Topic/How%20to:%20Add%20a%20Reference%20to%20a%20Web%20Service.md)|프로젝트에 XML\(ASMX\) 웹 서비스에 대한 참조를 추가하는 방법을 설명합니다.|  
|[Troubleshooting Service References](../data-tools/troubleshooting-service-references.md)|서비스 참조 시 발생할 수 있는 일반적인 오류와 이러한 오류를 방지하는 방법을 설명합니다.|  
|[WCF 서비스 디버깅](../debugger/debugging-wcf-services.md)|WCF 서비스를 디버깅할 때 발생할 수 있는 일반적인 디버깅 문제와 기술에 대해 설명합니다.|  
|[Windows Communication Foundation Authentication Service Overview](../Topic/Windows%20Communication%20Foundation%20Authentication%20Service%20Overview.md)|WCF를 사용하여 웹 사이트에 대한 역할 서비스를 제공하는 방법을 설명합니다.|  
|[Messaging in the .NET Compact Framework](http://msdn.microsoft.com/ko-kr/fb74d82c-f81e-46f9-aceb-f875c5c6be4f)|.NET Compact Framework에서 지원되는 WCF 메시징 계층에 대해 설명합니다.|  
|[연습: N 계층 데이터 응용 프로그램 만들기](../data-tools/walkthrough-creating-an-n-tier-data-application.md)|형식화된 데이터 집합을 만들고 TableAdapter와 데이터 집합 코드를 여러 프로젝트로 분리하기 위한 단계별 지침을 제공합니다.|  
|[Add Service Reference Dialog Box](../Topic/Add%20Service%20Reference%20Dialog%20Box.md)|**서비스 참조 추가** 대화 상자의 사용자 인터페이스 요소에 대해 설명합니다.|  
|[서비스 참조 구성 대화 상자](../data-tools/configure-service-reference-dialog-box.md)|**서비스 참조 구성** 대화 상자의 사용자 인터페이스 요소에 대해 설명합니다.|  
  
## 참조  
 <xref:System.ServiceModel>  
  
 <xref:System.Data.Services>