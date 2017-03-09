---
title: "연습: 자동화를 사용하여 Visual Studio SDK 호출 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "연습[Visual Studio SDK], 자동화를 사용하여 호출"
ms.assetid: ca4dab48-632c-4c2a-8c84-57c027e37987
caps.latest.revision: 31
caps.handback.revision: 31
manager: "douge"
---
# 연습: 자동화를 사용하여 Visual Studio SDK 호출
이 연습에서는 Visual Studio 서비스를 사용하는 Visual Studio 추가 기능을 만드는 방법을 보여 줍니다. 만든 추가 기능은 서비스 공급자를 가져오고 서비스를 얻는 데 사용합니다. 동일한 기법을 사용하여 제공되는 모든 Visual Studio 서비스를 가져올 수 있습니다. 서비스와 서비스 공급자에 대한 자세한 내용은 [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)를 참조하세요. 아래 절차에서는 추가 기능을 만든 다음 추가 기능에서 서비스를 가져오는 방법을 보여 줍니다.  
  
## 추가 기능 만들기  
 이 섹션에서는 Visual Studio 추가 기능 프로젝트 템플릿을 사용하여 Visual Studio 추가 기능을 만듭니다.  
  
#### 추가 기능을 만들려면  
  
1.  새 Visual Studio 프로젝트를 만듭니다\(**파일\/새로 만들기\/프로젝트**\).  
  
2.  **새 프로젝트** 대화 상자의 왼쪽 창에서 **기타 프로젝트 형식** 노드를 확장하고 **확장성** 노드를 클릭합니다.**Visual Studio 추가 기능**을 선택합니다.  
  
3.  `Addin`라는 새 추가 기능 프로젝트를 만듭니다.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 추가 기능 마법사에서 **다음**을 클릭합니다.  
  
4.  **프로그래밍 언어 선택** 페이지에서 **Visual C\#을 사용하여 추가 기능 만들기** 또는 **Visual Basic을 사용하여 추가 기능 만들기**를 선택합니다.  
  
5.  **응용 프로그램 호스트 선택** 페이지에서 **Microsoft Visual Studio \<version\>**을 선택합니다.  
  
6.  **이름 및 설명 입력** 페이지에서 **이름** 상자에 `MyAddin`를 입력하고 **설명** 상자에 `MyAddin Walkthrough`을 입력합니다.  
  
7.  **추가 기능 옵션 선택** 페이지의 **추가 기능에 사용할 명령 모음 UI를 만드시겠습니까?** 아래에서 도구 메뉴 항목에 대한 옵션을 선택합니다. 다른 확인란의 선택을 취소합니다.  
  
8.  다른 모든 기본값을 적용합니다.  
  
9. 솔루션을 빌드하고 오류 없이 컴파일되는지 확인합니다.  
  
## 추가 기능에서 서비스 가져오기  
 다음 단계는 추가 기능에서 서비스를 가져오는 과정을 안내합니다.  
  
#### 서비스를 가져오려면  
  
1.  Connect.cs 파일 또는 Connect.vb 파일을 열고 `using`\(C\#\) 또는 `Imports`\(Visual Basic\) 문에 다음 줄을 추가합니다.  
  
     [!CODE [VSSDKAddin#1](../CodeSnippet/VS_Snippets_VSSDK/vssdkaddin#1)]  
  
2.  **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 다음 .NET 참조를 추가합니다.  
  
    ```  
    Microsoft.VisualStudio.OLE.Interop Microsoft.VisualStudio.Shell.Interop  
    ```  
  
3.  `Exec` 메서드의 `if(commandName == "Addin.Connect.Addin")` 또는 `If commandName = "Addin.Connect.Addin" Then` 절에 다음 코드 줄을 추가합니다.  
  
     [!CODE [VSSDKAddin#2](../CodeSnippet/VS_Snippets_VSSDK/vssdkaddin#2)]  
  
     이 코드는 현재 응용 프로그램 개체\(`DTE2` 형식\)를 `IOleServiceProvider`로 캐스팅한 다음 `QueryService`를 호출하여 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> 서비스를 가져옵니다. 이 서비스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> 인터페이스를 제공합니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowMessageBox%2A> 메서드는 추가 기능이 실행될 때 메시지 상자를 표시합니다.  
  
4.  F5 키를 눌러 디버그 모드에서 Addin 프로젝트를 빌드하고 시작합니다.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 다른 인스턴스가 시작됩니다.  
  
5.  새 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 인스턴스의 **도구** 메뉴에서 **추가 기능**을 클릭합니다. 메시지 상자에 다음과 같이 표시됩니다.  
  
    ```  
    MyAddin Inside Addin.Connect  
    ```  
  
## 참고 항목  
 [How to: Deactivate and Remove an Add\-In](../Topic/How%20to:%20Deactivate%20and%20Remove%20an%20Add-In.md)