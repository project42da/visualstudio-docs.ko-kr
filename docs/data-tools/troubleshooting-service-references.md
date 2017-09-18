---
title: "Troubleshooting Service References | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msvse_wcf.Err.ReferenceGroup_NamespaceConflictsOther"
  - "msvse_wcf.Err.AddSvcRefDlg_NothingSelectedOnGo"
  - "msvse_wcf.Err.ErrorOnOK"
  - "msvse_wcf.cfg.ConfigurationErrorsException"
helpviewer_keywords: 
  - "service references [Visual Studio], troubleshooting"
  - "WCF services, troubleshooting"
ms.assetid: 3b531120-1325-4734-90c6-6e6113bd12ac
caps.latest.revision: 22
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Troubleshooting Service References
이 항목에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)] 또는 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] 참조를 사용하여 작업할 때 일반적으로 발생할 수 있는 문제에 대해 설명합니다.  
  
## 서비스에서 데이터를 반환할 때의 오류  
 서비스에서 `DataSet` 또는 `DataTable`을 반환할 때 "들어오는 메시지의 최대 크기 할당량을 초과했습니다.  기본적으로 일부 바인딩의 `MaxReceivedMessageSize` 속성은 서비스 거부 공격에 노출될 가능성을 줄이기 위해 비교적 작은 값으로 설정되어 있습니다.  이 값을 늘려 예외를 방지할 수 있습니다.  자세한 내용은 <xref:System.ServiceModel.BasicHttpBinding.MaxReceivedMessageSize%2A>를 참조하십시오.  
  
 이 오류를 해결하려면 다음을 수행합니다.  
  
1.  **솔루션 탐색기**에서 app.config 파일을 두 번 클릭하여 엽니다.  
  
2.  `MaxReceivedMessageSize` 속성을 찾아 더 큰 값으로 바꿉니다.  
  
## 솔루션에서 서비스를 찾을 수 없는 경우  
 **서비스 참조 추가** 대화 상자에서 **검색** 단추를 클릭할 때 솔루션에 있는 하나 이상의 WCF 서비스 라이브러리 프로젝트가 서비스 목록에 표시되지 않습니다.  이 문제는 서비스 라이브러리를 솔루션에 추가했지만 아직 컴파일하지 않은 경우에 발생할 수 있습니다.  
  
 이 오류를 해결하려면 다음을 수행합니다.  
  
-   **솔루션 탐색기**에서 WCF 서비스 라이브러리 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다.  
  
## 원격 데스크톱을 통해 서비스에 액세스하는 경우 발생하는 오류  
 사용자가 웹에 호스팅된 WCF 서비스에 원격 데스크톱 연결을 통해 액세스하는 경우 관리자 권한이 없으면 NTLM 인증이 사용됩니다.  사용자에게 관리자 권한이 없으면 "HTTP 요청이 클라이언트 인증 체계 'Anonymous'\(으\)로 인증되지 않습니다.  서버에서 수신한 인증 헤더가 'NTLM'입니다."라는 오류 메시지가 표시됩니다.  
  
 이 오류를 해결하려면 다음을 수행합니다.  
  
1.  웹 사이트 프로젝트에서 **속성** 페이지를 엽니다.  
  
2.  **시작 옵션** 탭에서 **NTLM 인증** 확인란의 선택을 취소합니다.  
  
    > [!NOTE]
    >  WCF 서비스만 포함된 웹 사이트에 대해서만 NTLM 인증을 해제해야 합니다.  그 이유는 WCF 서비스에 대한 보안은 web.config 파일의 구성을 통해 관리되므로  NTLM 인증을 사용하지 않아도 되기 때문입니다.  
  
 자세한 내용은 [예외 문제 해결: System.ServiceModel.Security.MessageSecurityException](../misc/troubleshooting-exceptions-system-servicemodel-security-messagesecurityexception.md)을 참조하십시오.  
  
## 생성된 클래스에 대한 액세스 수준 설정이 적용되지 않는 문제  
 **서비스 참조 구성** 대화 상자에서 **생성된 클래스에 대한 액세스 수준** 옵션을 **내부** 또는 **Friend**로 설정해도 효과가 없는 경우가 있습니다.  대화 상자에는 이 옵션이 설정된 것으로 표시되지만 결과 지원 클래스는 액세스 수준이 `Public`인 상태로 생성됩니다.  
  
 이 문제는 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize되는 형식 등 특정 형식의 알려진 제한 사항입니다.  
  
## 서비스 코드를 디버깅할 때의 오류  
 클라이언트 코드에서 WCF 서비스의 코드를 한 단계씩 실행할 경우 누락된 기호와 관련된 오류가 발생할 수 있습니다.  솔루션의 일부였던 서비스가 이동했거나 솔루션에서 제거된 경우 이 오류가 발생할 수 있습니다.  
  
 현재 솔루션의 일부인 WCF 서비스에 대한 참조를 먼저 추가한 경우 서비스 프로젝트와 서비스 클라이언트 프로젝트 간에 명시적 빌드 종속성이 추가됩니다.  따라서 클라이언트는 항상 최신 서비스 바이너리에 액세스할 수 있으며 이것은 특히 클라이언트 코드에서 서비스 코드를 한 단계씩 실행하는 경우와 같은 디버깅 시나리오에 중요합니다.  
  
 서비스 프로젝트가 솔루션에서 제거될 경우 이 명시적 빌드 종속성이 무효가 됩니다.  따라서 필요에 따라 서비스 프로젝트를 다시 빌드하는 작업이 더 이상 수행되지 않을 수도 있습니다.  
  
 이 오류를 해결하려면 서비스 프로젝트를 수동으로 다시 빌드해야 합니다.  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  **옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장한 다음 **일반**을 선택합니다.  
  
3.  **고급 빌드 구성 표시** 확인란이 선택되어 있는지 확인하고 **확인**을 클릭합니다.  
  
4.  WCF 서비스 프로젝트를 로드합니다.  자세한 내용은 [방법: 다중 프로젝트 솔루션 만들기](http://msdn.microsoft.com/ko-kr/02ecd6dd-0114-46fe-b335-ba9c5e3020d6)를 참조하십시오.  
  
5.  **구성 관리자** 대화 상자에서 **활성 솔루션 구성**을 **디버그**로 설정합니다.  자세한 내용은 [방법: 구성 만들기 및 편집](../ide/how-to-create-and-edit-configurations.md)을 참조하십시오.  
  
6.  **솔루션 탐색기**에서 WCF 서비스 프로젝트를 선택합니다.  
  
7.  **빌드** 메뉴에서 **다시 빌드**를 클릭하여 WCF 서비스 프로젝트를 다시 빌드합니다.  
  
## WCF 데이터 서비스가 브라우저에 표시되지 않음  
 [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)]에 있는 데이터의 XML 표현이 표시될 때 Internet Explorer에서 이 데이터를 RSS 피드로 잘못 해석할 수 있습니다.  RSS 피드를 표시하는 옵션은 반드시 비활성화되어 있어야 합니다.  
  
 이 오류를 해결하려면 다음과 같이 RSS 피드를 비활성화합니다.  
  
1.  Internet Explorer의 **도구** 메뉴에서 **인터넷 옵션**을 클릭합니다.  
  
2.  **내용** 탭의 **피드** 섹션에서 **설정**을 클릭합니다.  
  
3.  **피드 설정** 대화 상자에서 **피드 읽기용 보기 사용** 확인란의 선택을 취소하고 **확인**을 클릭합니다.  
  
4.  **확인**을 클릭하여 **인터넷 옵션** 대화 상자를 닫습니다.  
  
## 참고 항목  
 [Windows Communication Foundation Services and WCF Data Services in Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)   
 [Consuming ASMX and WCF Services Sample](http://msdn.microsoft.com/ko-kr/788ddf2c-2ac1-416b-8789-2fbb1e29b8fe)