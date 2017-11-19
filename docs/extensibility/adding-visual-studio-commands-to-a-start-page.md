---
title: "시작 페이지에 Visual Studio 명령 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- start page commands
- vs:VSCommands
ms.assetid: a8e2765c-cfb5-47b5-a414-6e48b434e0c2
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 973e0cfbceb6cbf67c5bc11cdde370607334809a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="adding-visual-studio-commands-to-a-start-page"></a>시작 페이지에 Visual Studio 명령 추가
사용자 지정 시작 페이지를 만들 때 Visual Studio 명령에 추가할 수 있습니다. 이 문서에서는 Visual Studio 명령 시작 페이지에서 XAML 개체를 바인딩할는 여러 가지 방법을 설명 합니다.  
  
 XAML의 명령에 대 한 자세한 내용은 참조 [명령 실행 개요](/dotnet/framework/wpf/advanced/commanding-overview)  
  
## <a name="adding-commands-from-the-command-well"></a>도 명령에서 명령 추가  
 시작 페이지에서 만든 [사용자 지정 시작 페이지 만들기](../extensibility/creating-a-custom-start-page.md) 추가 <xref:Microsoft.VisualStudio.PlatformUI?displayProperty=fullName> 및 <xref:Microsoft.VisualStudio.Shell?displayProperty=fullName> 다음과 같이 네임 스페이스입니다.  
  
```  
xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"  
xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"  
```  
  
 Microsoft.VisualStudio.Shell.Immutable.11.0.dll 어셈블리에서 Microsoft.VisualStudio.Shell에 대 한 다른 네임 스페이스를 추가 합니다. (프로젝트에서이 어셈블리에 대 한 참조를 추가 하려면 할 수 있습니다.)  
  
```xml  
xmlns:vscom="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.Immutable.11.0"  
```  
  
 사용할 수는 `vscom:` 에 XAML에서 Visual Studio 명령 바인딩할 별칭을 설정 하 여 페이지에 있는 컨트롤의 <xref:System.Windows.Controls.Primitives.ButtonBase.Command%2A> 컨트롤의 속성 `vscom:VSCommands.ExecuteCommand`합니다. 그런 다음 설정할 수는 <xref:System.Windows.Controls.Primitives.ButtonBase.CommandParameter%2A> 속성을 다음 예제와 같이 실행할 명령의 이름입니다.  
  
```xml  
<Button Name="btnNewProj" Content="New Project"   
    Command="{x:Static vscom:VSCommands.ExecuteCommand}"  
    CommandParameter="File.NewProject" >  
</Button>  
```  
  
> [!NOTE]
>  `x:` XAML 스키마를 가리키는 별칭은 모든 명령 맨 앞에 필요 합니다.  
  
 값을 설정할 수는 `Command` 속성에서 액세스할 수 있는 명령에는 **명령** 창. 사용 가능한 명령 목록을 참조 하십시오. [Visual Studio 명령 별칭](../ide/reference/visual-studio-command-aliases.md)합니다.  
  
 추가할 명령을 추가 매개 변수를 필요한 경우의 값에 추가할 수 있습니다는 `CommandParameter` 속성입니다. 다음 예제에 표시 된 대로 공간을 사용 하 여 명령에서 별도 매개 변수입니다.  
  
```xml  
<Button Content="Web Search"   
        Command="{x:Static vscom:VSCommands.ExecuteCommand}"  
        CommandParameter="View.WebBrowser www.bing.com" />  
```  
  
### <a name="calling-extensions-from-the-command-well"></a>명령에서 확장을 제대로 호출  
 다른 Visual Studio 명령을 호출 하는 데 사용 되는 동일한 구문을 사용 하 여 등록 된 Vspackage에서 명령을 호출할 수 있습니다. 예를 들어, 설치 된 VSPackage를 추가 하는 경우는 **홈 페이지** 명령을에 **보기** 메뉴에서 설정 하 여 해당 명령을 호출할 수 `CommandParameter` 를 `View.HomePage`합니다.  
  
> [!NOTE]
>  VSPackage에 연관 된 명령을 호출 하는 경우 패키지 명령이 호출 될 때 로드 되어야 합니다.  
  
## <a name="adding-commands-from-assemblies"></a>어셈블리의 명령 추가  
 메뉴 명령과 사용 하 여 연결 되지 않은 VSPackage에 액세스 코드 또는 어셈블리에서를 명령을 호출 하려면 어셈블리에 대 한 별칭을 만들어 하며 별칭을 호출 합니다.  
  
#### <a name="to-call-a-command-from-an-assembly"></a>어셈블리에서 명령을 호출 하려면  
  
1.  프로젝트가 솔루션의 어셈블리에 대 한 참조를 추가 합니다.  
  
2.  StartPage.xaml 파일 맨 위에 있는 다음 예제와 같이는 어셈블리에 대 한 네임 스페이스 지시문을 추가 합니다.  
  
    ```xml  
    xmlns:vsc="clr-namespace:WebUserControl;assembly=WebUserControl"  
    ```  
  
3.  명령을 설정 하 여 호출 된 `Command` 다음 예제와 같이 XAML 개체의 속성입니다.  
  
     Xaml  
  
    ```  
    <vs:Button Text="Hide me" Command="{x:Static vsc:HideControl}" .../>  
    ```  
  
> [!NOTE]
>  어셈블리를 복사 하며에 붙여 넣습니다. \\ *Visual Studio 설치 폴더*\Common7\IDE\PrivateAssemblies\ 호출 되기 전에 로드 되도록 합니다.  
  
## <a name="adding-commands-with-the-dte-object"></a>DTE 개체와 명령 추가  
 DTE 개체에서 시작 페이지, 태그와 코드에서 액세스할 수 있습니다.  
  
 태그에서 액세스할 수를 사용 하 여는 [바인딩 태그 확장](/dotnet/framework/wpf/advanced/binding-markup-extension) 호출 하는 구문을 <xref:EnvDTE.DTE> 개체입니다. 이 방법을 사용을 사용 하 여 컬렉션을 반환 하는 것과 같은 간단한 속성에 바인딩할 수 있지만 메서드 또는 서비스에 바인딩할 수 없습니다. 다음 예제와 <xref:System.Windows.Controls.TextBlock> 에 바인딩되는 컨트롤은 <xref:EnvDTE._DTE.Name%2A> 속성 및 <xref:System.Windows.Controls.ListBox> 를 열거 하는 컨트롤은 <xref:EnvDTE.Window.Caption%2A> 속성에서 반환 되는 컬렉션의는 <xref:EnvDTE._DTE.Windows%2A> 속성입니다.  
  
```xml  
<TextBlock Text="{Binding Path=DTE.Name}" FontSize="12" HorizontalAlignment="Center"/>  
<ListBox ItemsSource="{Binding Path=DTE.Windows}">  
    <ListBox.ItemTemplate>  
        <DataTemplate>  
            <TextBlock Text="{Binding Path=Caption}"/>  
        </DataTemplate>  
    </ListBox.ItemTemplate>  
</ListBox  
```  
  
 예를 들어 참조 [연습: 시작 페이지에서 사용자 설정 저장](../extensibility/walkthrough-saving-user-settings-on-a-start-page.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작 페이지에 사용자 컨트롤 추가](../extensibility/adding-user-control-to-the-start-page.md)