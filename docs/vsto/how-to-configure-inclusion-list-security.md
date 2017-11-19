---
title: "방법: 포함 목록 보안 구성 | Microsoft Docs"
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
- permissions [Office development in Visual Studio
- inclusion lists [Office development in Visual Studio]
ms.assetid: 0609d8f0-4630-4e17-aeb3-14f3134165cf
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7032f3663be7df1a06fa4dc16d4f4473e4666cfc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-configure-inclusion-list-security"></a>방법: 포함 목록 보안 구성
  관리자 권한이 있는 경우 구성할 수 있습니다는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트 컨트롤에 최종 사용자가 신뢰 결정 포함 목록에 저장 하 여 Office 솔루션을 설치할 수 제공할지 여부를 합니다. 포함 목록에 대 한 정보를 참조 하십시오. [포함 목록을 사용 하 여 Office 솔루션 신뢰](../vsto/trusting-office-solutions-by-using-inclusion-lists.md)합니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 5 개의 각 영역에 있는 솔루션의 경우 다음 옵션을 설정할 수 있습니다.  
  
-   사용 하도록 설정 된 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트 키와 포함 목록입니다. 모든 인증서로 서명 된 Office 솔루션에 신뢰를 부여할 최종 사용자가 허용할 수 있습니다.  
  
-   제한 된 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트 키와 포함 목록입니다. 게시자를 식별 하는 사용할 수 있지만 이미 신뢰할 수 있는 인증서로 서명 된 Office 솔루션을 설치 하려면 최종 사용자가 허용할 수 있습니다.  
  
-   사용 하지 않도록 설정 된 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트 키와 포함 목록입니다. 가 명시적으로 신뢰할 수 있는 인증서로 서명 되지 않은 모든 Office 솔루션을 설치할 최종 사용자가 방지할 수 있습니다.  
  
## <a name="enabling-the-inclusion-list"></a>포함 목록을 사용 하도록 설정  
 최종 사용자가을 설치 하 고 해당 영역에서 제공 되는 Office 솔루션을 실행 하는 옵션과 함께 표시 하려는 경우 포함 목록 영역에 대 한 사용 하도록 설정 합니다.  
  
#### <a name="to-enable-the-inclusion-list-by-using-the-registry-editor"></a>레지스트리 편집기를 사용 하 여 포함 목록을 사용 하도록 설정 하려면  
  
1.  레지스트리 편집기를 엽니다.  
  
    1.  클릭 **시작**, 클릭 하 고 **실행**합니다.  
  
    2.  에 **열려** 상자에 입력 합니다 **regedt32.exe**, 클릭 하 고 **확인**합니다.  
  
2.  다음 레지스트리 키를 찾습니다.  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\합니다. NETFramework\Security\TrustManager\PromptingLevel  
  
     키가 없는 경우 만듭니다.  
  
3.  다음 하위 키를 추가 **문자열 값**이미 없는, 관련된 값으로 하는 경우.  
  
    |문자열 값 하위 키|값|  
    |-------------------------|-----------|  
    |**인터넷**|**AuthenticodeRequired**|  
    |**UntrustedSites**|**사용 안 함**|  
    |**내 컴퓨터**|**사용**|  
    |**LocalIntranet**|**사용**|  
    |**TrustedSites**|**사용**|  
  
     기본적으로 **인터넷** 값 **AuthenticodeRequired** 및 **UntrustedSites** 값 **비활성화**합니다.  
  
#### <a name="to-enable-the-inclusion-list-programmatically"></a>포함 목록을 프로그래밍 방식으로 사용 하도록 설정 하려면  
  
1.  Visual Basic 또는 Visual C# 콘솔 응용 프로그램을 만듭니다.  
  
2.  편집을 위해 Program.cs 또는 Program.vb 파일을 열고 다음 코드를 추가 합니다.  
  
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
  
3.  응용 프로그램을 빌드 및 실행합니다.  
  
## <a name="restricting-the-inclusion-list"></a>포함 목록 제한  
 포함 목록 하도록 제한 하 솔루션은 사용자가 신뢰 여부를 결정 하기 전 까지의 알려진 id가 있는 Authenticode 인증서로 서명 되어야 합니다.  
  
#### <a name="to-restrict-the-inclusion-list"></a>포함 목록을 제한 하려면  
  
1.  레지스트리 편집기를 엽니다.  
  
    1.  클릭 **시작**, 클릭 하 고 **실행**합니다.  
  
    2.  에 **열려** 상자에 입력 합니다 **regedt32.exe**, 클릭 하 고 **확인**합니다.  
  
2.  다음 레지스트리 키를 찾습니다.  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\합니다. NETFramework\Security\TrustManager\PromptingLevel  
  
     키가 없는 경우 만듭니다.  
  
3.  다음 하위 키를 추가 **문자열 값**이미 없는, 관련된 값으로 하는 경우.  
  
    |문자열 값 하위 키|값|  
    |-------------------------|-----------|  
    |**UntrustedSites**|**사용 안 함**|  
    |**인터넷**|**AuthenticodeRequired**|  
    |**내 컴퓨터**|**AuthenticodeRequired**|  
    |**LocalIntranet**|**AuthenticodeRequired**|  
    |**TrustedSites**|**AuthenticodeRequired**|  
  
     기본적으로 **인터넷** 값 **AuthenticodeRequired** 및 **UntrustedSites** 값 **비활성화**합니다.  
  
#### <a name="to-restrict-the-inclusion-list-programmatically"></a>포함 목록을 프로그래밍 방식으로 제한 하려면  
  
1.  Visual Basic 또는 Visual C# 콘솔 응용 프로그램을 만듭니다.  
  
2.  편집을 위해 Program.cs 또는 Program.vb 파일을 열고 다음 코드를 추가 합니다.  
  
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
  
3.  응용 프로그램을 빌드 및 실행합니다.  
  
## <a name="disabling-the-inclusion-list"></a>포함 목록을 사용 하지 않도록 설정  
 최종 사용자가 알려지고 신뢰할 수 있는 인증서로 서명 된 솔루션에만 설치할 수 있도록 포함 목록을 해제할 수 있습니다.  
  
#### <a name="to-disable-the-inclusion-list"></a>포함 목록을 사용 하지 않도록 설정 하려면  
  
1.  레지스트리 편집기를 엽니다.  
  
    1.  클릭 **시작**, 클릭 하 고 **실행**합니다.  
  
    2.  에 **열려** 상자에 입력 합니다 **regedt32.exe**, 클릭 하 고 **확인**합니다.  
  
2.  이 존재 하지 않는 경우 다음 레지스트리 키를 만듭니다.  
  
     **\HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\합니다. NETFramework\Security\TrustManager\PromptingLevel**  
  
3.  다음 하위 키를 추가 **문자열 값**이미 없는, 관련된 값으로 하는 경우.  
  
    |문자열 값 하위 키|값|  
    |-------------------------|-----------|  
    |**UntrustedSites**|**사용 안 함**|  
    |**인터넷**|**사용 안 함**|  
    |**내 컴퓨터**|**사용 안 함**|  
    |**LocalIntranet**|**사용 안 함**|  
    |**TrustedSites**|**사용 안 함**|  
  
#### <a name="to-disable-the-inclusion-list-programmatically"></a>포함 목록을 프로그래밍 방식으로 사용 하지 않도록 설정 하려면  
  
1.  Visual Basic 또는 Visual C# 콘솔 응용 프로그램을 만듭니다.  
  
2.  편집을 위해 Program.cs 또는 Program.vb 파일을 열고 다음 코드를 추가 합니다.  
  
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
  
3.  응용 프로그램을 빌드 및 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [포함 목록을 사용 하 여 Office 솔루션 신뢰](../vsto/trusting-office-solutions-by-using-inclusion-lists.md)   
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)  
  
  