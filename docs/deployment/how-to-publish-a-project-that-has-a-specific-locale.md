---
title: "방법: 특정 로캘이 지정 된 프로젝트 게시 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publishing, localized projects
- locales, publishing for
- deploying applications [ClickOnce], localized projects
- locales, deploying for
- publishing localized projects
- macros, deploying with
- macros, publishing with
ms.assetid: 7c4cd83a-f985-4c85-9022-fadb5dbd2b39
caps.latest.revision: "11"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: b2560275ae08a9a860d62f11e0fb011e5e7a5b31
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-publish-a-project-that-has-a-specific-locale"></a>방법: 특정 로캘이 지정된 프로젝트 게시
응용 프로그램에 포함된 구성 요소가 서로 다른 로캘을 사용하는 경우를 흔히 볼 수 있습니다. 이러한 시나리오에서는 여러 프로젝트가 포함된 솔루션을 만든 다음 각 로캘에 대해 프로젝트를 별도로 게시합니다. 아래 절차에서는 매크로를 통해 'en' 로캘을 사용하는 솔루션의 첫 번째 프로젝트를 게시하는 방법을 보여줍니다. 'en' 이외의 로캘에 대해 이 절차를 수행하려면 매크로의 `localeString`을 'de' 또는 'de-DE'와 같이 사용 중인 로캘과 일치하도록 설정합니다.  
  
> [!NOTE]
>  이 매크로를 사용할 때 게시 위치는 올바른 URL 또는 UNC(범용 명명 규칙) 공유여야 합니다. 또한 IIS(인터넷 정보 서비스)가 컴퓨터에 설치되어 있어야 합니다. IIS를 설치 하는 **시작** 메뉴를 클릭 **제어판**합니다. 두 번 클릭 **프로그램 추가 / 제거**합니다. **프로그램 추가 / 제거**, 클릭 **Windows 구성 요소 추가/제거**합니다. 에 **Windows 구성 요소 마법사**, 선택는 **인터넷 정보 서비스 (IIS)** 확인란에는 **구성 요소** 목록. 클릭 **마침** 마법사를 닫습니다.  
  
### <a name="to-create-the-publishing-macro"></a>게시 매크로를 만들려면  
  
1.  매크로 탐색기에서 열려는 **도구** 메뉴에서 **매크로**, 클릭 하 고 **매크로 탐색기**합니다.  
  
2.  새 매크로 모듈을 만듭니다. 매크로 탐색기에서 선택 **MyMacros**합니다. 에 **도구** 메뉴에서 **매크로**, 클릭 하 고 **새 매크로 모듈**합니다. 모듈의 이름을 **publishspecificculture로 지정**합니다.  
  
3.  매크로 탐색기에서 확장 된 **MyMacros** 노드를 연 후는 **PublishAllProjects** 두 번 클릭 하 여 모듈 (또는에서 **도구** 메뉴에서 **매크로**, 클릭 하 고 **매크로 IDE**).  
  
4.  매크로 IDE에서 모듈의 `Import` 문 뒤에 다음 코드를 추가합니다.  
  
    ```vb  
    Module PublishSpecificCulture  
        Sub PublishProjectFirstProjectWithEnLocale()  
            ' Note: You should publish projects by using the IDE at least once  
            ' before you use this macro. Items such as the certficate and the   
            ' security zone must be set.  
            Dim localeString As String = "en"  
  
            ' Get first project.  
            Dim proj As Project = DTE.Solution.Projects.Item(1)  
            Dim publishProperties As Object = proj.Properties.Item("Publish").Value  
  
            ' GenerateManifests and SignManifests must always be set to  
            ' True for publishing to work.   
            proj.Properties.Item("GenerateManifests").Value = True  
            proj.Properties.Item("SignManifests").Value = True  
  
            'Set the publish language.  
            'This will set the deployment language and pick up all   
            ' en resource dlls:  
            Dim originalTargetCulture As String = _  
                publishProperties.Item("TargetCulture").Value  
            publishProperties.Item("TargetCulture").Value = localeString  
  
            'Append 'en' to end of publish, install, and update URLs if needed:  
            Dim originalPublishUrl As String = _  
                publishProperties.Item("PublishUrl").Value  
            Dim originalInstallUrl As String = _  
                publishProperties.Item("InstallUrl").Value  
            Dim originalUpdateUrl As String = _  
                publishProperties.Item("UpdateUrl").Value  
            publishProperties.Item("PublishUrl").Value = _  
                AppendStringToUrl(localeString, New Uri(originalPublishUrl))  
            If originalInstallUrl <> String.Empty Then  
                publishProperties.Item("InstallUrl").Value = _  
                    AppendStringToUrl(localeString, New Uri(originalInstallUrl))  
            End If  
            If originalUpdateUrl <> String.Empty Then  
                publishProperties.Item("UpdateUrl").Value = _  
                    AppendStringToUrl(localeString, New Uri(originalUpdateUrl))  
            End If  
            proj.Save()  
  
            Dim slnbld2 As SolutionBuild2 = _  
                CType(DTE.Solution.SolutionBuild, SolutionBuild2)  
            slnbld2.Clean(True)  
  
            slnbld2.BuildProject( _  
            proj.ConfigurationManager.ActiveConfiguration.ConfigurationName, _  
            proj.UniqueName, True)  
  
            ' Only publish if build is successful.  
            If slnbld2.LastBuildInfo <> 0 Then  
                MsgBox("Build failed for " & proj.UniqueName)  
            Else  
                slnbld2.PublishProject( _  
                proj.ConfigurationManager.ActiveConfiguration.ConfigurationName, _  
                proj.UniqueName, True)  
                If slnbld2.LastPublishInfo = 0 Then  
                    MsgBox("Publish succeeded for " & proj.UniqueName _  
                    & vbCrLf & "." _  
                    & " Publish Language was '" & localeString & "'.")  
                Else  
                    MsgBox("Publish failed for " & proj.UniqueName)  
                End If  
            End If  
  
            ' Return URLs and target culture to their previous state.  
            publishProperties.Item("PublishUrl").Value = originalPublishUrl  
            publishProperties.Item("InstallUrl").Value = originalInstallUrl  
            publishProperties.Item("UpdateUrl").Value = originalUpdateUrl  
            publishProperties.Item("TargetCulture").Value = originalTargetCulture  
            proj.Save()  
        End Sub  
  
        Private Function AppendStringToUrl(ByVal str As String, _  
        ByVal baseUri As Uri) As String  
            Dim returnValue As String = baseUri.OriginalString  
            If baseUri.IsFile OrElse baseUri.IsUnc Then  
                returnValue = IO.Path.Combine(baseUri.OriginalString, str)  
            Else  
                If Not baseUri.ToString.EndsWith("/") Then  
                    returnValue = baseUri.OriginalString & "/" & str  
                Else  
                    returnValue = baseUri.OriginalString & str  
                End If  
            End If  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
5.  매크로 IDE를 닫습니다. 포커스가 다시 Visual Studio로 돌아옵니다.  
  
### <a name="to-publish-a-project-for-a-specific-locale"></a>특정 로캘에 대한 프로젝트를 게시하려면  
  
1.  에 Visual Basic Windows 응용 프로그램 프로젝트를 만들려면는 **파일** 메뉴에서 **새로**, 클릭 하 고 **프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 **Windows 응용 프로그램** 에서 **Visual Basic** 노드. 프로젝트 이름을 **PublishLocales**합니다.  
  
3.  Form1을 클릭합니다. 에 **속성** 창 아래에서 **디자인**, 변경의 **언어** 속성 **(기본값)** 를 **영어**. 변경의 **텍스트** 속성 폼의 **MyForm**합니다.  
  
     지역화된 리소스 DLL은 필요할 때까지 만들어지지 않습니다. 예를 들어 새 로캘을 지정한 후 폼의 텍스트 또는 해당 컨트롤 중 하나를 변경하면 이러한 DLL이 만들어집니다.  
  
4.  Visual Studio IDE를 사용하여 PublishLocales를 게시합니다.  
  
     **솔루션 탐색기**, PublishLocales를 선택 합니다. 에 **프로젝트** 메뉴 선택 **속성**합니다. 프로젝트 디자이너에서에 **게시** 페이지에서의 게시 위치 지정 **http://localhost/PublishLocales**, 클릭 하 고 **지금 게시**합니다.  
  
     게시 웹 페이지가 표시되면 닫습니다. 이 단계에서는 프로젝트를 게시만 하면 되며 설치할 필요는 없습니다.  
  
5.  Visual Studio 명령 프롬프트 창에서 매크로를 호출하여 PublishLocales를 다시 게시합니다. 명령 프롬프트 창에서 보려는 **보기** 메뉴에서 **다른 창** 클릭 하 고 **명령 창**, 하거나 CTRL + ALT + A를 누릅니다. 명령 프롬프트 창에서 입력 `macros`자동 완성 기능 사용 가능한 매크로의 목록이 제공 됩니다. 다음 매크로를 선택하고 Enter 키를 누릅니다.  
  
     `Macros.MyMacros.PublishSpecificCulture.PublishProjectFirstProjectWithEnLocale`  
  
6.  게시 프로세스가 정상적으로 완료되면 "PublishLocales\PublishLocales.vbproj를 게시했습니다. 게시 언어는 'en'입니다."라는 메시지가 표시됩니다. 클릭 **확인** 메시지 상자에 있습니다. 게시 웹 페이지가 나타나면 클릭 **설치**합니다.  
  
7.  C:\Inetpub\wwwroot\PublishLocales\en을 확인합니다. 지역화된 리소스 DLL 외에 매니페스트, setup.exe, 게시 웹 페이지 파일 등의 설치된 파일이 표시되어야 합니다. ClickOnce는 기본적으로 EXE 및 DLL에 대해 .deploy 확장명을 추가합니다. 배포 후에 이 확장명을 제거할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [매크로 개발 환경](http://msdn.microsoft.com/en-us/d23105d8-34fe-4ad9-8278-fae2c660aeac)   
 [매크로 탐색기 창](http://msdn.microsoft.com/en-us/762169e6-f83f-44b4-bffa-d0f107cae9a3)   
 [방법: 편집 및 매크로 프로그래밍 방식으로 만들기](http://msdn.microsoft.com/en-us/6716f820-1feb-48ad-a718-27eb6b473c5a)