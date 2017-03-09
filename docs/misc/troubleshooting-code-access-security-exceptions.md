---
title: "코드 액세스 보안 예외 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "CodeAccessPermission 클래스"
  - "CodeAccessSecurityException 클래스"
  - "코드 액세스 보안, 문제 해결"
  - "보안[디버거], 코드 액세스 보안 문제 해결"
  - "코드 액세스 보안 문제 해결"
ms.assetid: ca368d3b-f6d0-4c89-af59-d94f343fca35
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 코드 액세스 보안 예외 문제 해결
사용 권한은 코드로 수행할 수 있는 작업과 수행할 수 없는 작업을 제어합니다. 응용 프로그램이 실행되면 런타임에 의해 권한 집합이 부여됩니다. 사용 권한이 충분하면 응용 프로그램이 제대로 실행되지만, 그렇지 않으면 보안 예외가 발생합니다.  
  
 코드에 부여되는 사용 권한은 인터넷, 인트라넷, 로컬 컴퓨터와 같이 응용 프로그램이 실행되는 위치와 응용 프로그램이 실행되는 컴퓨터의 보안 설정에 따라 결정됩니다. 이러한 설정은 컴퓨터마다 다를 수 있으므로 코드에 충분한 사용 권한이 부여될지 여부를 항상 예측할 수는 없습니다.  
  
 사용 권한을 요청하면 로컬 컴퓨터의 보안 정책에서 허용되는 경우 코드를 실행할 수 있습니다. 필요한 사용 권한을 요청하지 않으면 코드가 실행되지 않을 위험을 감수해야 합니다. 코드 액세스 권한과 이를 요청하는 방법에 대한 자세한 내용은 [코드 액세스 권한](http://msdn.microsoft.com/ko-kr/e5ae402f-6dda-4732-bbe8-77296630f675) 또는 [NIB: 권한 요청](http://msdn.microsoft.com/ko-kr/0447c49d-8cba-45e4-862c-ff0b59bebdc2)을 참조하세요.`Try...Catch` 블록에 대한 자세한 내용은 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)을 참조하세요.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에서는 필요한 경우 응용 프로그램 디자이너의 보안 페이지를 통해 사용 권한을 추가로 요청할 수 있습니다. 자세한 내용은 [방법: ClickOnce 응용 프로그램에 대한 사용자 지정 권한 설정](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)을 참조하세요.  
  
 코드 액세스 보안 예외는 다음과 같은 원인으로 발생할 수 있습니다.  
  
-   **클립보드.** 클립보드에 중요한 정보가 포함될 수도 있으므로 관리 코드에서는 프로그래밍 방식으로 클립보드에서 붙여넣는 기능이 제한됩니다.  
  
-   **레지스트리 또는 파일 시스템 액세스.** 로컬 파일 시스템에 대한 액세스가 제한되어 있습니다. 어셈블리와 함께 배포된 파일이나 리소스에 액세스하려는 경우에는 `Assembly.GetExecutingAssembly.Location` 코드를 사용하여 어셈블리의 경로를 가져와야 합니다.  
  
-   **네트워크 액세스.** 어셈블리를 로드할 때 사용한 것과 동일한 프로토콜을 어셈블리에서 사용해야 합니다. 일반적으로 네트워크 통신은 어셈블리의 출처인 URL에 대해서만 허용됩니다.  
  
-   **인쇄.** 인터넷 영역에서 실행되는 소프트웨어는 일반 대화 상자를 통해서만 인쇄할 수 있습니다. 사용자가 프린터를 선택할 수 있도록 허용하는 일반 대화 상자를 사용하는 경우에 한해서 기본 프린터만 사용할 수 있도록 제한되어 있습니다.  
  
-   **serialization.** 임의의 데이터로부터 개체를 다시 만드는 기능은 완전 신뢰 수준으로 실행되는 코드에서만 사용할 수 있습니다. XML serialization의 경우 부분 신뢰 코드에서도 기술적으로는 `XmlSerializer` 형식을 사용할 수 있습니다.`XmlSerializer` 형식에 대한 자세한 내용은 [XmlSerializer 클래스](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)를 참조하세요.  
  
-   **리플렉션.** 부분 신뢰 코드에서는 런타임의 리플렉션 관련 기능을 대부분 사용할 수 없습니다.  
  
## 코드 액세스 보안 예외를 throw할지 확인하기 위한 코드 테스트  
 코드 블록에서 `CodeAccessSecurityException`을 throw할 가능성이 있는 경우 `Try...Catch` 블록을 사용하여 실행 가능한 경우 코드를 실행하고 실행 불가능한 경우 문제를 해결합니다.  
  
 호스트 시스템에서 허용한 사용 권한에 따라 동작을 조정하도록 응용 프로그램을 디자인할 수도 있습니다. 예를 들어, 응용 프로그램에 인쇄 권한이 없으면 메뉴에서 인쇄 명령을 비활성화할 수 있습니다.  
  
 권한이 있는지 테스트하려면 `CodeAccessPermission`과 같이 `FileIOPermission` 파생 클래스의 인스턴스를 만듭니다. 그런 다음 `Demand` 블록 안에서 이 사용 권한에 대해 `Try...Catch` 메서드를 실행합니다. 예외가 throw되면 어셈블리에 사용 권한이 없는 것입니다.  
  
 다음 예제에서는 `EventLogPermission`을 실행하거나 만들고 `EventLogPermission` 블록 안에서 해당 `Demand` 메서드를 실행하여 `Try...Catch`에서 예외가 발생하는지 확인하는 방식으로 어셈블리에 `Demand` 권한이 있는지 여부를 테스트합니다.  
  
```  
Try Dim MyPermission As New EventLogPermission MyPermission.Demand() MsgBox(MyPermission.ToString()) Catch ex As Exception MsgBox("Assembly lacks EventLogPermission.") End Try  
```  
  
## 참고 항목  
 [코드 액세스 권한](http://msdn.microsoft.com/ko-kr/e5ae402f-6dda-4732-bbe8-77296630f675)   
 [NIB: 권한 요청](http://msdn.microsoft.com/ko-kr/0447c49d-8cba-45e4-862c-ff0b59bebdc2)   
 [코드 액세스 보안 기본 사항](../Topic/Code%20Access%20Security%20Basics.md)