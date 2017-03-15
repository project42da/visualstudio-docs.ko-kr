---
title: "Sent 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.ServiceModel.Activities.Send.UI"
ms.assetid: b514f2e4-767c-4b94-ac61-dd3a54d4b96d
caps.latest.revision: 7
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Sent 활동 디자이너
**Send** 활동 디자이너는 <xref:System.ServiceModel.Activities.Send> 활동을 만들고 구성하는 데 사용됩니다.  
  
## Send 활동  
 <xref:System.ServiceModel.Activities.Send> 활동은 서비스에 메시지를 보내는 데 사용됩니다.<xref:System.ServiceModel.Activities.ReceiveReply> 활동은 클라이언트 측에서 요청\/응답 메시지 교환 패턴 중 메시지를 받는 <xref:System.ServiceModel.Activities.Send> 활동에 바인딩될 수 있습니다.  
  
### Send 활동 디자이너 사용  
 **Send** 활동 디자이너는 **도구 상자**의 **메시징** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **도구 상자**의 **Send** 활동 디자이너를 끌어다가 일반적으로 활동을 배치하는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에나 놓을 수 있습니다.그러면 기본 <xref:System.Activities.Activity.DisplayName%2A>인 Send라는 이름의 <xref:System.ServiceModel.Activities.Send> 활동이 만들어집니다.**Send** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 <xref:System.Activities.Activity.DisplayName%2A>을 편집할 수 있습니다.  
  
 <xref:System.ServiceModel.Activities.ReceiveReply> 활동을 만들어 선택한 <xref:System.ServiceModel.Activities.Send> 활동에 바인딩하려면 **Send** 활동 디자이너를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **ReceiveReply 만들기** 항목을 클릭합니다. 그러면 **ReceiveReplyForSend** 디자이너가 **Send** 디자이너 아래에 나타납니다.<xref:System.ServiceModel.Activities.ReceiveReply> 활동은 요청\/응답 메시지 교환 패턴 중 클라이언트에서 메시지를 받는 활동입니다.이 활동은 **ReceiveReplyForSend** 디자이너를 사용하여 구성할 수 있습니다.  
  
 또는 **도구 상자**의 **메시징** 범주에서 **SendAndReceiveReply** 템플릿 디자이너를 사용하여 사전 구성된  <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 활동 쌍을 만들 수 있습니다.**SendAndReceiveReply** 및 **ReceiveReplyForSend** 템플릿 사용 [!INCLUDE[crabout](../test/includes/crabout_md.md)][SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) 항목을 참조하십시오.  
  
### Send 활동 속성  
 다음 표에서는 <xref:System.ServiceModel.Activities.Send> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.이러한 속성은 속성 표 또는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|용도|  
|-----------|--------|--------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.Send> 활동의 이름입니다.기본값은 Send입니다.<xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
|<xref:System.ServiceModel.Activities.Send.OperationName%2A>|True|이 <xref:System.ServiceModel.Activities.Send> 활동에 의해 호출되는 서비스 작업의 이름입니다.**Action** 속성이 명시적으로 설정되어 있지 않으면 이 속성을 사용하여 **Action** 속성의 기본값을 구성합니다.|  
|<xref:System.ServiceModel.Activities.Send.ServiceContractName%2A>|True|호출할 서비스가 구현하는 서비스 계약의 이름입니다.|  
|<xref:System.ServiceModel.Activities.Send.Content%2A>|False|받을 메시지 또는 매개 변수 콘텐츠를 지정합니다.<xref:System.ServiceModel.Activities.ReceiveMessageContent> 활동이거나 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 활동일 수 있습니다.속성 표의 **콘텐츠** 필드 옆에 있는 줄임표 단추를 클릭하거나 **Receive** 활동 디자이너 화면의 **콘텐츠** 레이블 옆에 있는 **정의…** 단추를 클릭하여 이 속성을 편집할 수 있습니다.둘 모두 **콘텐츠 정의** 대화 상자를 표시합니다.이 상자를 사용하는 방법 [!INCLUDE[crabout](../test/includes/crabout_md.md)][콘텐츠 정의 대화 상자](../workflow-designer/content-definition-dialog-box.md) 항목을 참조하십시오.|  
|<xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A>|False|메시지를 적절한 워크플로 인스턴스로 라우팅하는 데 사용되는 <xref:System.ServiceModel.Activities.CorrelationHandle>을 지정합니다.<br /><br /> <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> 속성 옆의 줄임표 단추를 클릭하여 **식 편집기** 대화 상자를 엽니다.이 상자를 사용하는 방법 [!INCLUDE[crabout](../test/includes/crabout_md.md)][방법: 식 편집기 사용](../workflow-designer/how-to-use-the-expression-editor.md) 항목을 참조하십시오.|  
|<xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A>|False|워크플로 내에서 이 <xref:System.ServiceModel.Activities.Send> 활동을 구성하는 <xref:System.ServiceModel.Activities.CorrelationHandle> 개체를 여러 개 초기화하는 <xref:System.ServiceModel.Activities.CorrelationInitializer> 개체 컬렉션을 지정합니다.속성 표에서 <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> 속성 옆의 줄임표 단추를 클릭하여 **상관 관계 이니셜라이저 추가** 대화 상자를 엽니다.이 상자를 사용하는 방법 [!INCLUDE[crabout](../test/includes/crabout_md.md)][상관 관계 이니셜라이저 추가 대화 상자](../workflow-designer/add-correlationinitializers-dialog-box.md) 항목을 참조하십시오.|  
|<xref:System.ServiceModel.Activities.Send.KnownTypes%2A>|False|이 <xref:System.ServiceModel.Activities.Send> 활동으로 호출되는 서비스 작업에 대한 알려진 형식의 컬렉션입니다.이 속성은 <xref:System.Runtime.Serialization.DataContractSerializer>로 설정된 <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> 속성과 함께 사용해야 합니다.<xref:System.Xml.Serialization.XmlSerializer>를 사용하는 경우 무시됩니다.<br /><br /> 속성 표의 **KnownTypes** 필드 옆에 있는 줄임표 단추를 클릭하여 관련 형식을 추가할 수 있는 **형식 컬렉션 편집기** 대화 상자를 표시합니다.<br /><br /> 속성 표의 **KnownTypes** 필드 옆에 있는 줄임표 단추를 클릭하여 관련 형식을 추가할 수 있는 **형식 컬렉션 편집기** 대화 상자를 표시합니다.이 상자를 사용하는 방법 [!INCLUDE[crabout](../test/includes/crabout_md.md)][형식 컬렉션 편집기 대화 상자](../workflow-designer/type-collection-editor-dialog-box.md) 항목을 참조하십시오.|  
|<xref:System.ServiceModel.Activities.Send.ProtectionLevel%2A>|True|메시지의 <xref:System.Net.Security.ProtectionLevel>을 지정합니다.<br /><br /> 1.  <xref:System.Net.Security.ProtectionLevel>은 인증만 사용하는 것을 의미합니다.<br />2.  <xref:System.Net.Security.ProtectionLevel>은 전송된 데이터의 무결성을 확인할 수 있도록 데이터에 서명하는 것입니다.<br />3.  <xref:System.Net.Security.ProtectionLevel>은 전송된 데이터의 기밀성과 무결성을 확인할 수 있도록 데이터를 암호화하고 서명하는 것입니다.|  
|<xref:System.ServiceModel.Activities.Send.SerializerOption%2A>|True|<xref:System.ServiceModel.Activities.Send> 활동으로 호출되는 서비스 작업에 사용할 serializer입니다.기본값은 <xref:System.Runtime.Serialization.DataContractSerializer>이며, 제공된 데이터 계약을 사용하여 형식 인스턴스를 XML 스트림 또는 문서로 serialize 및 deserialize합니다.|  
|<xref:System.ServiceModel.Activities.Send.Action%2A>|False|메시지의 동작 헤더를 지정합니다.명시적으로 설정하지 않은 경우 기본값인 https:\/\/tempuri.org\/{service contract namespace}\/{service contract name}\/{operation name}이 사용됩니다.<xref:System.ServiceModel.Activities.Send> 활동에 지정하는 경우 메시지를 받는 <xref:System.ServiceModel.Activities.Receive> 활동에 동일한 값이 있어야 메시지가 올바르게 배달됩니다.|  
|<xref:System.ServiceModel.Activities.Send.TokenImpersonationLevel%2A>||메시지 수신자에게 허용되는 <xref:System.Security.Principal.TokenImpersonationLevel>입니다.클라이언트 프로세스 대신 서버 프로세스를 수행할 수 있는 정도를 지정하는 보안 가장 수준을 정의합니다.<xref:System.Security.Principal.TokenImpersonationLevel>은 가장 수준이 지정되지 않았음을 의미하고,<xref:System.Security.Principal.TokenImpersonationLevel>는 서버 프로세스에서 클라이언트의 식별 정보를 확보할 수 없어 해당 클라이언트를 가장할 수 없음을 의미합니다.<xref:System.Security.Principal.TokenImpersonationLevel>은 서버 프로세스에서 보안 식별자 및 권한과 같은 클라이언트 관련 정보를 확보할 수 있지만 해당 클라이언트를 가장할 수 없음을 의미합니다.이 기능은 자체 개체를 내보내는 서버\(예: 테이블과 뷰를 내보내는 데이터베이스 제품\)에 유용합니다.서버는 검색된 클라이언트 보안 정보를 사용하여 클라이언트의 보안 컨텍스트를 사용하는 다른 서비스를 사용할 수는 없지만 액세스 위반 결정을 내릴 수 있습니다.<xref:System.Security.Principal.TokenImpersonationLevel>은 서버 프로세스에서 로컬 시스템의 클라이언트 보안 컨텍스트를 가장할 수 있음을 의미합니다.원격 시스템에서는 서버가 클라이언트를 가장할 수 없습니다.<xref:System.Security.Principal.TokenImpersonationLevel>은 서버 프로세스에서 원격 시스템의 클라이언트 보안 컨텍스트를 가장할 수 있음을 의미합니다.|  
|<xref:System.ServiceModel.Activities.Send.Endpoint%2A>||<xref:System.ServiceModel.Activities.Send> 활동에서 메시지를 보내는 <xref:System.ServiceModel.Endpoint>입니다.이 속성이 설정되면 <xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> 속성은 **null**이어야 합니다.|  
|<xref:System.ServiceModel.Activities.Send.EndpointAddress%2A>||메시지가 전달될 <xref:System.ServiceModel.EndpointAddress>입니다.|  
|<xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A>||끝점 구성의 이름입니다.이 속성은 구성 파일에서 끝점을 구성할 때 설정됩니다.이 속성은 구성 파일에서 **\<endpoint\>** 요소에 지정된 이름으로 설정되어야 합니다.이 속성이 설정되면 <xref:System.ServiceModel.Activities.Send.Endpoint%2A> 속성은 **null**이어야 합니다.|  
  
## 참고 항목  
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [Receive](../workflow-designer/receive-activity-designer.md)   
 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)