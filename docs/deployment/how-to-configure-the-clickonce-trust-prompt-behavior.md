---
title: "방법: ClickOnce 신뢰 프롬프트 동작 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 응용 프로그램, 메시지를 표시하지 않고 설치"
  - "ClickOnce 응용 프로그램, 신뢰 프롬프트"
  - "ClickOnce 배포, 메시지를 표시하지 않고 설치"
  - "ClickOnce 배포, 신뢰 프롬프트"
  - "응용 프로그램 배포[ClickOnce], 신뢰 프롬프트"
ms.assetid: cc04fa75-012b-47c9-9347-f4216be23cf2
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ClickOnce 신뢰 프롬프트 동작 구성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

최종 사용자가 Windows Forms 응용 프로그램, Windows Presentation Foundation 응용 프로그램, 콘솔 응용 프로그램, WPF 브라우저 응용 프로그램 및 Office 솔루션 같은 ClickOnce 응용 프로그램을 설치할 수 있는지 여부를 제어하도록 ClickOnce 신뢰 프롬프트를 구성할 수 있습니다.  신뢰 프롬프트는 각 최종 사용자의 컴퓨터에서 레지스트리 키를 설정하여 구성합니다.  
  
 다음 표에서는 5개의 각 영역\(Internet, UntrustedSites, MyComputer, LocalIntranet, TrustedSites\)에 적용할 수 있는 구성 옵션을 보여 줍니다.  
  
|옵션|레지스트리 설정 값|설명|  
|--------|----------------|--------|  
|신뢰 프롬프트를 사용하도록 설정합니다.|`Enabled`|최종 사용자가 ClickOnce 응용 프로그램에 신뢰를 부여할 수 있도록 ClickOnce 신뢰 프롬프트가 표시됩니다.|  
|신뢰 프롬프트를 제한합니다.|`AuthenticodeRequired`|ClickOnce 응용 프로그램이 게시자를 식별하는 인증서로 서명된 경우에만 ClickOnce 신뢰 프롬프트가 표시됩니다.|  
|신뢰 프롬프트를 사용하지 않도록 설정합니다.|`Disabled`|명시적으로 신뢰할 수 있는 인증서로 서명되지 않은 ClickOnce 응용 프로그램의 경우 ClickOnce 신뢰 프롬프트가 표시되지 않습니다.|  
  
 다음 표에서는 각 영역의 기본 동작을 보여 줍니다.  응용 프로그램 열은 Windows Forms 응용 프로그램, Windows Presentation Foundation 응용 프로그램, WPF 브라우저 응용 프로그램 및 콘솔 응용 프로그램을 나타냅니다.  
  
|영역|응용 프로그램|Office 솔루션|  
|--------|-------------|----------------|  
|`MyComputer`|`Enabled`|`Enabled`|  
|`LocalIntranet`|`Enabled`|`Enabled`|  
|`TrustedSites`|`Enabled`|`Enabled`|  
|`Internet`|`Enabled`|`AuthenticodeRequired`|  
|`UntrustedSites`|`Disabled`|`Disabled`|  
  
 ClickOnce 신뢰 프롬프트를 사용하도록 설정하거나 제한하거나 사용하지 않도록 설정하여 이 설정을 재정의할 수 있습니다.  
  
## ClickOnce 신뢰 프롬프트를 사용하도록 설정  
 최종 사용자가 특정 영역에서 가져온 ClickOnce 응용 프로그램을 설치하고 실행할 수 있도록 하려면 해당 영역에 대해 신뢰 프롬프트를 사용하도록 설정합니다.  
  
#### 레지스트리 편집기를 사용하여 ClickOnce 신뢰 프롬프트를 사용하도록 설정하려면  
  
1.  레지스트리 편집기를 엽니다.  
  
    1.  **시작**을 클릭한 다음 **실행**을 클릭합니다.  
  
    2.  **열기** 상자에 `regedit32`를 입력한 다음 **확인**을 클릭합니다.  
  
2.  다음 레지스트리 키를 찾습니다.  
  
     \\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel  
  
     해당 키가 없으면 만듭니다.  
  
3.  **문자열 값**으로 다음 하위 키가 아직 없으면 해당 하위 키와 다음 표에 나와 있는 관련 값을 추가합니다.  
  
    |문자열 값 하위 키|값|  
    |----------------|-------|  
    |`Internet`|`Enabled`|  
    |`UntrustedSites`|`Disabled`|  
    |`MyComputer`|`Enabled`|  
    |`LocalIntranet`|`Enabled`|  
    |`TrustedSites`|`Enabled`|  
  
     Office 솔루션의 경우 `Internet`에는 기본값인 `AuthenticodeRequired`가 지정되고 `UntrustedSites`에는 `Disabled` 값이 지정됩니다.  나머지 경우에는 모두 `Internet`에 기본값인 `Enabled`가 지정됩니다.  
  
#### ClickOnce 신뢰 프롬프트를 프로그램 방식으로 사용하도록 지정하려면  
  
1.  Visual Studio에서 Visual Basic 또는 Visual C\# 콘솔 응용 프로그램을 만듭니다.  
  
2.  편집할 Program.vb 또는 Program.cs 파일을 열고 다음 코드를 추가합니다.  
  
    ```vb#  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Enabled")  
    key.SetValue("LocalIntranet", "Enabled")  
    key.SetValue("Internet", "Enabled")  
    key.SetValue("TrustedSites", "Enabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```c#  
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
  
## ClickOnce 신뢰 프롬프트 제한  
 사용자에게 신뢰 여부를 결정하라는 메시지가 표시되기 전에 알려진 ID가 있는 Authenticode 인증서로 솔루션에 서명해야만 하도록 신뢰 프롬프트를 제한할 수 있습니다.  
  
#### 레지스트리 편집기를 사용하여 ClickOnce 신뢰 프롬프트를 제한하려면  
  
1.  레지스트리 편집기를 엽니다.  
  
    1.  **시작**을 클릭한 다음 **실행**을 클릭합니다.  
  
    2.  **열기** 상자에 `regedit`를 입력한 다음 **확인**을 클릭합니다.  
  
2.  다음 레지스트리 키를 찾습니다.  
  
     \\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel  
  
     해당 키가 없으면 만듭니다.  
  
3.  **문자열 값**으로 다음 하위 키가 아직 없으면 해당 하위 키와 다음 표에 나와 있는 관련 값을 추가합니다.  
  
    |문자열 값 하위 키|값|  
    |----------------|-------|  
    |`UntrustedSites`|`Disabled`|  
    |`Internet`|`AuthenticodeRequired`|  
    |`MyComputer`|`AuthenticodeRequired`|  
    |`LocalIntranet`|`AuthenticodeRequired`|  
    |`TrustedSites`|`AuthenticodeRequired`|  
  
#### ClickOnce 신뢰 프롬프트를 프로그램 방식으로 제한하려면  
  
1.  Visual Studio에서 Visual Basic 또는 Visual C\# 콘솔 응용 프로그램을 만듭니다.  
  
2.  편집할 Program.vb 또는 Program.cs 파일을 열고 다음 코드를 추가합니다.  
  
    ```vb#  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "AuthenticodeRequired")  
    key.SetValue("LocalIntranet", "AuthenticodeRequired")  
    key.SetValue("Internet", "AuthenticodeRequired")  
    key.SetValue("TrustedSites", "AuthenticodeRequired")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```c#  
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
  
## ClickOnce 신뢰 프롬프트를 사용하지 않도록 설정  
 최종 사용자가 보안 정책에서 아직 신뢰되지 않은 솔루션을 설치할 수 없도록 신뢰 프롬프트를 사용하지 않도록 설정할 수 있습니다.  
  
#### 레지스트리 편집기를 사용하여 ClickOnce 신뢰 프롬프트를 사용하지 않도록 설정하려면  
  
1.  레지스트리 편집기를 엽니다.  
  
    1.  **시작**을 클릭한 다음 **실행**을 클릭합니다.  
  
    2.  **열기** 상자에 `regedit`를 입력한 다음 **확인**을 클릭합니다.  
  
2.  다음 레지스트리 키를 찾습니다.  
  
     \\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel  
  
     해당 키가 없으면 만듭니다.  
  
3.  **문자열 값**으로 다음 하위 키가 아직 없으면 해당 하위 키와 다음 표에 나와 있는 관련 값을 추가합니다.  
  
    |문자열 값 하위 키|값|  
    |----------------|-------|  
    |`UntrustedSites`|`Disabled`|  
    |`Internet`|`Disabled`|  
    |`MyComputer`|`Disabled`|  
    |`LocalIntranet`|`Disabled`|  
    |`TrustedSites`|`Disabled`|  
  
#### ClickOnce 신뢰 프롬프트를 프로그램 방식으로 사용하지 않도록 지정하려면  
  
1.  Visual Studio에서 Visual Basic 또는 Visual C\# 콘솔 응용 프로그램을 만듭니다.  
  
2.  편집할 Program.vb 또는 Program.cs 파일을 열고 다음 코드를 추가합니다.  
  
    ```vb#  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Disabled")  
    key.SetValue("LocalIntranet", "Disabled")  
    key.SetValue("Internet", "Disabled")  
    key.SetValue("TrustedSites", "Disabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```c#  
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
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)   
 [ClickOnce 응용 프로그램의 코드 액세스 보안](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce 및 Authenticode](../deployment/clickonce-and-authenticode.md)   
 [신뢰할 수 있는 응용 프로그램 배포 개요](../deployment/trusted-application-deployment-overview.md)   
 [방법: ClickOnce 보안 설정 사용](../deployment/how-to-enable-clickonce-security-settings.md)   
 [방법: ClickOnce 응용 프로그램의 보안 영역 설정](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [방법: ClickOnce 응용 프로그램에 대한 사용자 지정 권한 설정](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [방법: 제한된 권한으로 ClickOnce 응용 프로그램 디버깅](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [방법: ClickOnce 응용 프로그램의 클라이언트 컴퓨터에 신뢰할 수 있는 게시자 추가](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)   
 [방법: 응용 프로그램 및 배포 매니페스트에 다시 서명](../deployment/how-to-re-sign-application-and-deployment-manifests.md)