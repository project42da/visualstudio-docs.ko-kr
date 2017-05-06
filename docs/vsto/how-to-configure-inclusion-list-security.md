---
title: "방법: 포함 목록 보안 구성"
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
  - "포함 목록[Visual Studio에서 Office 개발]"
  - "권한[Visual Studio에서 Office 개발]"
ms.assetid: 0609d8f0-4630-4e17-aeb3-14f3134165cf
caps.latest.revision: 26
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 25
---
# 방법: 포함 목록 보안 구성
  관리자 권한이 있는 경우 신뢰 결정을 포함 목록에 저장하여 최종 사용자가 Office 솔루션을 설치할 수 있는지 여부를 제어하는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트를 구성할 수 있습니다.  포함 목록에 대한 자세한 내용은 [포함 목록을 사용하여 Office 솔루션 신뢰](../vsto/trusting-office-solutions-by-using-inclusion-lists.md)를 참조하십시오.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 5개의 각 영역에 있는 솔루션의 경우 다음 옵션을 설정할 수 있습니다.  
  
-   [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트 키와 포함 목록을 사용하도록 설정합니다.  이렇게 하면 모든 인증서로 서명된 Office 솔루션에 최종 사용자가 신뢰를 부여할 수 있습니다.  
  
-   [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트 키와 포함 목록을 제한합니다.  이렇게 하면 게시자를 식별하지만 아직 신뢰되지 않은 인증서로 서명된 Office 솔루션을 최종 사용자가 설치할 수 있습니다.  
  
-   [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트 키와 포함 목록을 사용하지 않도록 설정합니다.  이렇게 하면 최종 사용자가 명시적으로 신뢰된 인증서로 서명되지 않은 Office 솔루션을 설치할 수 없습니다.  
  
## 포함 목록을 사용하도록 설정  
 최종 사용자가 특정 영역에서 가져온 Office 솔루션을 설치하고 실행할 수 있도록 하려면 해당 영역의 포함 목록을 사용하도록 설정합니다.  
  
#### 레지스트리 편집기를 사용하여 포함 목록을 사용하도록 설정하려면  
  
1.  레지스트리 편집기를 엽니다.  
  
    1.  **시작**을 클릭한 다음 **실행**을 클릭합니다.  
  
    2.  **열기** 상자에 **regedt32.exe**를 입력한 다음 **확인**을 클릭합니다.  
  
2.  다음 레지스트리 키를 찾습니다.  
  
     \\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel  
  
     해당 키가 없으면 만듭니다.  
  
3.  **문자열 값**으로 다음 하위 키가 아직 없으면 해당 하위 키와 관련 값을 추가합니다.  
  
    |문자열 값 하위 키|값|  
    |----------------|-------|  
    |**Internet**|**AuthenticodeRequired**|  
    |**UntrustedSites**|**Disabled**|  
    |**MyComputer**|**Enabled**|  
    |**LocalIntranet**|**Enabled**|  
    |**TrustedSites**|**Enabled**|  
  
     기본적으로 **Internet**에는 **AuthenticodeRequired** 값이 지정되고 **UntrustedSites**에는 **Disabled** 값이 지정됩니다.  
  
#### 프로그래밍 방식으로 포함 목록을 사용하도록 설정하려면  
  
1.  Visual Basic 또는 Visual C\# 콘솔 응용 프로그램을 만듭니다.  
  
2.  편집할 Program.vb 또는 Program.cs 파일을 열고 다음 코드를 추가합니다.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Enabled")  
    key.SetValue("LocalIntranet", "Enabled")  
    key.SetValue("Internet", "AuthenticodeRequired")  
    key.SetValue("TrustedSites", "Enabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Enabled");  
    key.SetValue("LocalIntranet", "Enabled");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "Enabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  응용 프로그램을 빌드하고 실행합니다.  
  
## 포함 목록 제한  
 사용자에게 신뢰 여부를 결정하라는 메시지가 표시되기 전에 알려진 ID가 있는 Authenticode 인증서로 솔루션에 서명해야만 하도록 포함 목록을 제한할 수 있습니다.  
  
#### 포함 목록을 제한하려면  
  
1.  레지스트리 편집기를 엽니다.  
  
    1.  **시작**을 클릭한 다음 **실행**을 클릭합니다.  
  
    2.  **열기** 상자에 **regedt32.exe**를 입력한 다음 **확인**을 클릭합니다.  
  
2.  다음 레지스트리 키를 찾습니다.  
  
     \\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel  
  
     해당 키가 없으면 만듭니다.  
  
3.  **문자열 값**으로 다음 하위 키가 아직 없으면 해당 하위 키와 관련 값을 추가합니다.  
  
    |문자열 값 하위 키|값|  
    |----------------|-------|  
    |**UntrustedSites**|**Disabled**|  
    |**Internet**|**AuthenticodeRequired**|  
    |**MyComputer**|**AuthenticodeRequired**|  
    |**LocalIntranet**|**AuthenticodeRequired**|  
    |**TrustedSites**|**AuthenticodeRequired**|  
  
     기본적으로 **Internet**에는 **AuthenticodeRequired** 값이 지정되고 **UntrustedSites**에는 **Disabled** 값이 지정됩니다.  
  
#### 프로그래밍 방식으로 포함 목록을 제한하려면  
  
1.  Visual Basic 또는 Visual C\# 콘솔 응용 프로그램을 만듭니다.  
  
2.  편집할 Program.vb 또는 Program.cs 파일을 열고 다음 코드를 추가합니다.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "AuthenticodeRequired")  
    key.SetValue("LocalIntranet", "AuthenticodeRequired")  
    key.SetValue("Internet", "AuthenticodeRequired")  
    key.SetValue("TrustedSites", "AuthenticodeRequired")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "AuthenticodeRequired");  
    key.SetValue("LocalIntranet", "AuthenticodeRequired");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "AuthenticodeRequired");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  응용 프로그램을 빌드하고 실행합니다.  
  
## 포함 목록을 사용하지 않도록 설정  
 최종 사용자가 신뢰되고 알려진 인증서로 서명된 솔루션만 설치할 수 있도록 하려면 포함 목록을 사용하지 않도록 설정합니다.  
  
#### 포함 목록을 사용하지 않도록 설정하려면  
  
1.  레지스트리 편집기를 엽니다.  
  
    1.  **시작**을 클릭한 다음 **실행**을 클릭합니다.  
  
    2.  **열기** 상자에 **regedt32.exe**를 입력한 다음 **확인**을 클릭합니다.  
  
2.  다음 레지스트리 키가 아직 없으면 만듭니다.  
  
     **\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel**  
  
3.  **문자열 값**으로 다음 하위 키가 아직 없으면 해당 하위 키와 관련 값을 추가합니다.  
  
    |문자열 값 하위 키|값|  
    |----------------|-------|  
    |**UntrustedSites**|**Disabled**|  
    |**Internet**|**Disabled**|  
    |**MyComputer**|**Disabled**|  
    |**LocalIntranet**|**Disabled**|  
    |**TrustedSites**|**Disabled**|  
  
#### 프로그래밍 방식으로 포함 목록을 사용하지 않도록 설정하려면  
  
1.  Visual Basic 또는 Visual C\# 콘솔 응용 프로그램을 만듭니다.  
  
2.  편집할 Program.vb 또는 Program.cs 파일을 열고 다음 코드를 추가합니다.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Disabled")  
    key.SetValue("LocalIntranet", "Disabled")  
    key.SetValue("Internet", "Disabled")  
    key.SetValue("TrustedSites", "Disabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Disabled");  
    key.SetValue("LocalIntranet", "Disabled");  
    key.SetValue("Internet", "Disabled");  
    key.SetValue("TrustedSites", "Disabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
  
    ```  
  
3.  응용 프로그램을 빌드하고 실행합니다.  
  
## 참고 항목  
 [포함 목록을 사용하여 Office 솔루션 신뢰](../vsto/trusting-office-solutions-by-using-inclusion-lists.md)   
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)  
  
  