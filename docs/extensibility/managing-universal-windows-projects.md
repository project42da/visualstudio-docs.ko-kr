---
title: "유니버설 Windows 프로젝트 관리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47926aa1-3b41-410d-bca8-f77fc950cbe7
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6fdb3585d0b2bba5daf248707fa2848d3d32dfdb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="managing-universal-windows-projects"></a>유니버설 Windows 프로젝트 관리
유니버설 Windows 앱은 Windows 8.1 및 Windows Phone 8.1, 때문에 두 플랫폼 모두에서 코드 및 기타 자산을 사용 하는 개발자가 모두 대상으로 하는 앱. 동안 플랫폼 관련 코드 및 리소스에 별도 프로젝트, Windows 및 Windows Phone 대 한 기타 보관 되는 공유 코드와 리소스 공유 프로젝트에 유지 됩니다. 유니버설 Windows 앱에 대 한 자세한 내용은 참조 [유니버설 Windows 앱](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx)합니다. Visual Studio 확장명 프로젝트를 관리 하는 유니버설 Windows 앱 프로젝트는 단일 플랫폼 앱과 다른 구조를 제공 해야 합니다. 이 연습에서는 공유 프로젝트를 탐색 하 고 공유 항목을 관리 하는 방법을 보여 줍니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
### <a name="navigate-the-shared-project"></a>공유 프로젝트를 이동 합니다.  
  
1.  라는 C# VSIX 프로젝트를 **TestUniversalProject**합니다. (**파일, 새로 만들기, 프로젝트** 차례로 **C#, 확장성, Visual Studio 패키지**). 추가 **사용자 지정 명령** 프로젝트 항목 템플릿을 (솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 / 새 항목**이동한 다음 **확장성**). 파일 이름을 **TestUniversalProject**합니다.  
  
2.  Microsoft.VisualStudio.Shell.Interop.12.1.DesignTime.dll Microsoft.VisualStudio.Shell.Interop.14.0.DesignTime.dll에 대 한 참조를 추가 (에 **확장** 섹션).  
  
3.  TestUniversalProject.cs를 열고 다음 코드를 추가 `using` 문:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.PlatformUI;  
    using Microsoft.Internal.VisualStudio.PlatformUI;   
    using System.Collections.Generic;   
    using System.IO;  
    using System.Windows.Forms;  
    ```  
  
4.  TestUniversalProject 클래스에서 가리키는 private 필드를 추가 하는 **출력** 창.  
  
    ```csharp  
    public sealed class TestUniversalProject   
    {  
        IVsOutputWindowPane output;  
    . . .  
    }  
    ```  
  
5.  TestUniversalProject 생성자 내부 출력 창에 대 한 참조를 설정 합니다.  
  
    ```csharp  
    private TestUniversalProject(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException("package");  
        }  
  
        this.package = package;  
  
        OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            CommandID menuCommandID = new CommandID(MenuGroup, CommandId);  
            EventHandler eventHandler = this.ShowMessageBox;  
            MenuCommand menuItem = new MenuCommand(eventHandler, menuCommandID);  
            commandService.AddCommand(menuItem);  
        }  
        // get a reference to the Output window  
                    output = (IVsOutputWindowPane)ServiceProvider.GetService(typeof(SVsGeneralOutputWindowPane));  
    }  
    ```  
  
6.  기존 코드를 제거는 `ShowMessageBox` 메서드:  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)   
    {  
    }  
    ```  
  
7.  이 연습에서는 여러 다른 용도로 사용 합니다 DTE 개체를 가져옵니다. 또한 메뉴 단추를 클릭할 때에 솔루션이 로드 되었는지 확인 합니다.  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {   
        var dte = (EnvDTE.DTE)this.ServiceProvider.GetService(typeof(EnvDTE.DTE));  
        if (dte.Solution != null)   
        {  
            . . .  
        }  
        else   
        {  
            MessageBox.Show("No solution is open");  
            return;   
        }  
    }  
    ```  
  
8.  공유 프로젝트를 찾습니다. 공유 프로젝트 컨테이너인 순수 작성 하거나 출력을 생성 하지 않습니다. 다음 메서드를 검색 하 여 솔루션에서 첫 번째 공유 프로젝트를 찾습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 공유 프로젝트 기능이 있는 개체입니다.  
  
    ```csharp  
    private IVsHierarchy FindSharedProject()  
    {  
        var sln = (IVsSolution)this.ServiceProvider.GetService(typeof(SVsSolution));  
        Guid empty = Guid.Empty;  
        IEnumHierarchies enumHiers;  
  
        //get all the projects in the solution  
        ErrorHandler.ThrowOnFailure(sln.GetProjectEnum((uint)__VSENUMPROJFLAGS.EPF_LOADEDINSOLUTION, ref empty, out enumHiers));  
        foreach (IVsHierarchy hier in ComUtilities.EnumerableFrom(enumHiers))  
        {  
            if (PackageUtilities.IsCapabilityMatch(hier, "SharedAssetsProject"))  
            {  
                return hier;  
            }  
        }  
        return null;  
    }  
    ```  
  
9. 에 `ShowMessageBox` 메서드 출력 캡션 (에 표시 되는 프로젝트 이름을 **솔루션 탐색기**) 공유 프로젝트.  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {  
        var dte = (DTE)this.ServiceProvider.GetService(typeof(DTE));  
  
        if (dte.Solution != null)  
        {  
            var sharedHier = this.FindSharedProject();  
            if (sharedHier != null)  
            {  
                string sharedCaption = HierarchyUtilities.GetHierarchyProperty<string>(sharedHier, (uint)VSConstants.VSITEMID.Root,  
                     (int)__VSHPROPID.VSHPROPID_Caption);  
                output.OutputStringThreadSafe(string.Format("Found shared project: {0}\n", sharedCaption));  
            }  
            else  
            {  
                MessageBox.Show("Solution has no shared project");  
                return;  
            }  
                }  
        else  
        {  
            MessageBox.Show("No solution is open");  
            return;  
        }  
    }  
    ```  
  
10. 활성 플랫폼 프로젝트를 가져옵니다. 플랫폼 프로젝트는 플랫폼 특정 코드 및 리소스를 포함 하는 프로젝트입니다. 새 필드를 사용 하는 다음 메서드 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID7> 활성 플랫폼 프로젝트를 얻으려고 합니다.  
  
    ```csharp  
    private IVsHierarchy GetActiveProjectContext(IVsHierarchy hierarchy)  
    {  
        IVsHierarchy activeProjectContext;  
        if (HierarchyUtilities.TryGetHierarchyProperty(hierarchy, (uint)VSConstants.VSITEMID.Root,  
             (int)__VSHPROPID7.VSHPROPID_SharedItemContextHierarchy, out activeProjectContext))  
        {  
            return activeProjectContext;  
        }  
        else  
        {  
            return null;  
        }  
    }  
    ```  
  
11. 에 `ShowMessageBox` 메서드를 활성 플랫폼 프로젝트의 캡션을 출력 합니다.  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {  
        var dte = (DTE)this.ServiceProvider.GetService(typeof(DTE));  
  
        if (dte.Solution != null)  
        {  
            var sharedHier = this.FindSharedProject();  
            if (sharedHier != null)  
            {  
                string sharedCaption = HierarchyUtilities.GetHierarchyProperty<string>(sharedHier, (uint)VSConstants.VSITEMID.Root,  
                     (int)__VSHPROPID.VSHPROPID_Caption);  
                output.OutputStringThreadSafe(string.Format("Shared project: {0}\n", sharedCaption));  
  
                var activePlatformHier = this.GetActiveProjectContext(sharedHier);  
                if (activePlatformHier != null)  
                {  
                    string activeCaption = HierarchyUtilities.GetHierarchyProperty<string>(activePlatformHier,  
                         (uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID.VSHPROPID_Caption);  
                    output.OutputStringThreadSafe(string.Format("Active platform project: {0}\n", activeCaption));  
                }  
                else  
                {  
                MessageBox.Show("Shared project has no active platform project");  
                }  
            }  
            else  
            {  
                MessageBox.Show("Solution has no shared project");  
                return;  
            }  
        }  
        else  
            {  
                MessageBox.Show("No solution is open");  
                return;  
            }  
        }  
  
    ```  
  
12. 플랫폼 프로젝트를 검색 합니다. 다음 메서드는 공유 프로젝트에서 모든 가져오기 (플랫폼) 프로젝트를 가져옵니다.  
  
    ```csharp  
    private IEnumerable<IVsHierarchy> EnumImportingProjects(IVsHierarchy hierarchy)  
    {  
        IVsSharedAssetsProject sharedAssetsProject;  
        if (HierarchyUtilities.TryGetHierarchyProperty(hierarchy, (uint)VSConstants.VSITEMID.Root,  
            (int)__VSHPROPID7.VSHPROPID_SharedAssetsProject, out sharedAssetsProject)  
            && sharedAssetsProject != null)  
        {  
            foreach (IVsHierarchy importingProject in sharedAssetsProject.EnumImportingProjects())  
            {  
                yield return importingProject;  
            }  
        }  
    }  
    ```  
  
    > [!IMPORTANT]
    >  사용자 실험적 인스턴스에서 c + + 유니버설 Windows 앱 프로젝트를 연 경우 위의 코드는 예외를 throw 합니다. 이것은 알려진 문제입니다. 예외를 방지 하려면 대체는 `foreach` 위에 다음으로 차단 합니다.  
  
    ```csharp  
    var importingProjects = sharedAssetsProject.EnumImportingProjects();  
    for (int i = 0; i < importingProjects.Count; ++i)  
    {  
        yield return importingProjects[i];  
    }   
    ```  
  
13. 에 `ShowMessageBox` 메서드를 각 플랫폼 프로젝트의 캡션을 출력 합니다. 활성 플랫폼 프로젝트의 캡션을 출력 하는 줄 뒤에 다음 코드를 삽입 합니다. 이 목록에 로드 되는 플랫폼 프로젝트만 표시 합니다.  
  
    ```csharp  
    output.OutputStringThreadSafe("Platform projects:\n");  
  
    IEnumerable<IVsHierarchy> projects = this.EnumImportingProjects(sharedHier);  
  
    bool isActiveProjectSet = false;  
    foreach (IVsHierarchy platformHier in projects)  
    {  
        string platformCaption = HierarchyUtilities.GetHierarchyProperty<string>(platformHier, (uint)VSConstants.VSITEMID.Root,  
            (int)__VSHPROPID.VSHPROPID_Caption);  
        output.OutputStringThreadSafe(string.Format(" * {0}\n", platformCaption));  
    }  
    ```  
  
14. 활성 플랫폼 프로젝트를 변경 합니다. 다음 메서드를 사용 하 여 현재 프로젝트 설정 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.SetProperty%2A>합니다.  
  
    ```csharp  
    private int SetActiveProjectContext(IVsHierarchy hierarchy, IVsHierarchy activeProjectContext)  
    {  
        return hierarchy.SetProperty((uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID7.VSHPROPID_SharedItemContextHierarchy, activeProjectContext);  
    }  
    ```  
  
15. 에 `ShowMessageBox` 메서드를 활성 플랫폼 프로젝트를 변경 합니다. 내에서이 코드를 삽입는 `foreach` 블록입니다.  
  
    ```csharp  
    bool isActiveProjectSet = false;  
    string platformCaption = null;  
    foreach (IVsHierarchy platformHier in projects)  
    {  
        platformCaption = HierarchyUtilities.GetHierarchyProperty<string>(platformHier, (uint)VSConstants.VSITEMID.Root,  
             (int)__VSHPROPID.VSHPROPID_Caption);  
        output.OutputStringThreadSafe(string.Format(" * {0}\n", platformCaption));  
  
        // if this project is neither the shared project nor the current active platform project,   
        // set it to be the active project  
        if (!isActiveProjectSet && platformHier != activePlatformHier)  
        {  
            this.SetActiveProjectContext(sharedHier, platformHier);  
            activePlatformHier = platformHier;  
            isActiveProjectSet = true;  
        }  
    }  
    output.OutputStringThreadSafe("set active project: " + platformCaption +'\n');  
    ```  
  
16. 이제 사용해 보세요. F5 키를 눌러 실험적 인스턴스를 시작할 수 있습니다. 실험적 인스턴스에서 C# 허브 유니버설 앱 프로젝트를 만듭니다 (에 **새 프로젝트** 대화 상자, **Visual C# / Windows / Windows 8 / 유니버설 / 허브 앱**). 솔루션을 로드 한 후로 이동는 **도구** 메뉴를 클릭 **TestUniversalProject 호출**, 한 다음 텍스트를 체크 인하는 **출력** 창. 다음과 같은 내용이 나타납니다.  
  
    ```  
    Found shared project: HubApp.Shared  
    The active platform project: HubApp.Windows  
    Platform projects:  
     * HubApp.Windows  
     * HubApp.WindowsPhone  
    set active project: HubApp.WindowsPhone  
    ```  
  
### <a name="manage-the-shared-items-in-the-platform-project"></a>플랫폼 프로젝트에서 공유 항목을 관리  
  
1.  플랫폼 프로젝트에서 공유 항목을 찾습니다. 공유 프로젝트에 있는 항목 플랫폼 프로젝트에서 공유 항목으로 나타납니다. 볼 수 없는 **솔루션 탐색기**, 하지만를 기다리며 프로젝트 계층 구조를 연습할 수 있습니다. 다음 메서드는 계층 구조를 설명 하 고 모든 공유 항목을 수집 합니다. 필요에 따라 각 항목의 캡션을 출력합니다. 공유 항목은 새 속성으로 식별 된 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID7>합니다.  
  
    ```csharp  
    private void InspectHierarchyItems(IVsHierarchy hier, uint itemid, int level, List<uint> itemIds, bool getSharedItems, bool printItems)  
    {  
        string caption = HierarchyUtilities.GetHierarchyProperty<string>(hier, itemid, (int)__VSHPROPID.VSHPROPID_Caption);  
        if (printItems)  
            output.OutputStringThreadSafe(string.Format("{0}{1}\n", new string('\t', level), caption));  
  
        // if getSharedItems is true, inspect only shared items; if it's false, inspect only unshared items  
        bool isSharedItem;  
        if (HierarchyUtilities.TryGetHierarchyProperty(hier, itemid, (int)__VSHPROPID7.VSHPROPID_IsSharedItem, out isSharedItem)  
            && (isSharedItem == getSharedItems))  
        {  
            itemIds.Add(itemid);  
        }  
  
        uint child;  
        if (HierarchyUtilities.TryGetHierarchyProperty(hier, itemid, (int)__VSHPROPID.VSHPROPID_FirstChild, Unbox.AsUInt32, out child)  
            && child != (uint)VSConstants.VSITEMID.Nil)  
        {  
            this.InspectHierarchyItems(hier, child, level + 1, itemIds, isSharedItem, printItems);  
  
            while (HierarchyUtilities.TryGetHierarchyProperty(hier, child, (int)__VSHPROPID.VSHPROPID_NextSibling, Unbox.AsUInt32, out child)  
                && child != (uint)VSConstants.VSITEMID.Nil)  
            {  
                this.InspectHierarchyItems(hier, child, level + 1, itemIds, isSharedItem, printItems);  
            }  
                    }  
    }  
    ```  
  
2.  에 `ShowMessageBox` 메서드를 플랫폼 프로젝트 계층 구조 항목을 안내 하는 다음 코드를 추가 합니다. 안에 삽입는 `foreach` 블록입니다.  
  
    ```csharp  
    output.OutputStringThreadSafe("Walk the active platform project:\n");  
    var sharedItemIds = new List<uint>();  
    this.InspectHierarchyItems(activePlatformHier, (uint)VSConstants.VSITEMID.Root, 1, sharedItemIds, true, true);  
    ```  
  
3.  공유 항목을 읽습니다. 공유 항목 플랫폼 프로젝트에 연결 된 숨겨진 파일로 나타나며 일반 연결 된 파일로 모든 속성을 읽을 수 있습니다. 다음 코드는 첫 번째 공유 항목의 전체 경로 읽습니다.  
  
    ```csharp  
    var sharedItemId = sharedItemIds[0];  
    string fullPath;  
    ErrorHandler.ThrowOnFailure(((IVsProject)activePlatformHier).GetMkDocument(sharedItemId, out fullPath));  
    output.OutputStringThreadSafe(string.Format("Shared item full path: {0}\n", fullPath));  
    ```  
  
4.  이제 사용해 보세요. F5 키를 눌러 실험적 인스턴스를 시작할 수 있습니다. 실험적 인스턴스에서 C# 허브 유니버설 앱 프로젝트를 만듭니다 (에 **새 프로젝트** 대화 상자, **Visual C# / Windows / Windows 8 / 유니버설 / 허브 앱**)로 이동는 **도구** 메뉴를 클릭 **호출 TestUniversalProject**, 한 다음 텍스트를 체크 인하는 **출력** 창. 다음과 같은 내용이 나타납니다.  
  
    ```  
    Found shared project: HubApp.Shared  
    The active platform project: HubApp.Windows  
    Platform projects:  
     * HubApp.Windows  
     * HubApp.WindowsPhone  
    set active project: HubApp.WindowsPhone  
    Walk the active platform project:  
        HubApp.WindowsPhone  
            <HubApp.Shared>  
                App.xaml  
                    App.xaml.cs  
                Assets  
                    DarkGray.png  
                    LightGray.png  
                    MediumGray.png  
                Common  
                    NavigationHelper.cs  
                    ObservableDictionary.cs  
                    RelayCommand.cs  
                    SuspensionManager.cs  
                DataModel  
                    SampleData.json  
                    SampleDataSource.cs  
                HubApp.Shared.projitems  
                Strings  
                    en-US  
                        Resources.resw  
            Assets  
                HubBackground.theme-dark.png  
                HubBackground.theme-light.png  
                Logo.scale-240.png  
                SmallLogo.scale-240.png  
                SplashScreen.scale-240.png  
                Square71x71Logo.scale-240.png  
                StoreLogo.scale-240.png  
                WideLogo.scale-240.png  
            HubPage.xaml  
                HubPage.xaml.cs  
            ItemPage.xaml  
                ItemPage.xaml.cs  
            Package.appxmanifest  
            Properties  
                AssemblyInfo.cs  
            References  
                .NET for Windows Store apps  
                HubApp.Shared  
                Windows Phone 8.1  
            SectionPage.xaml  
                SectionPage.xaml.cs  
    ```  
  
### <a name="detecting-changes-in-platform-projects-and-shared-projects"></a>플랫폼 프로젝트와 공유 프로젝트의 변경 내용 검색  
  
1.  플랫폼 프로젝트에 대 한 경우와 마찬가지로 공유 프로젝트의 변경 내용을 검색 하려면 계층 구조 및 프로젝트 이벤트를 사용할 수 있습니다. 그러나 공유 프로젝트에 프로젝트 항목이 표시 되지 않습니다, 즉, 공유 프로젝트 항목을 변경한 경우 때는 특정 이벤트가 발생 하지 않습니다.  
  
     프로젝트에서 파일의 이름을 바꿀 때의 이벤트 순서를 고려 합니다.  
  
    1.  디스크에 파일 이름이 변경 됩니다.  
  
    2.  프로젝트 파일은 파일의 새 이름을 포함 하도록 업데이트 됩니다.  
  
     계층 이벤트 (예를 들어 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents>) 일반적으로 변경 내용이에서 같이 UI에 표시 된 추적의 **솔루션 탐색기**합니다. 계층 이벤트 파일 삭제 한 다음 파일 추가 구성 파일 이름 바꾸기 작업을 고려 합니다. 그러나 보이지 않는 항목이 변경 되 면 계층 이벤트 시스템 발생 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A> 이벤트 하지 않고는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemAdded%2A> 이벤트입니다. 따라서 경우 플랫폼 프로젝트에서 파일의 이름을 바꾸면 얻게 둘 다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemAdded%2A>, 있어도 공유 프로젝트에 있는 파일의 이름을 바꾸면만 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A>합니다.  
  
     프로젝트 항목에 대 한 변경 내용을 추적 하기 DTE 프로젝트 항목 이벤트를 처리할 수 있습니다 (에서 찾을 수 있는 구성을 <xref:EnvDTE.ProjectItemsEventsClass>). 그러나 많은 수의 이벤트를 처리 하는 경우에 이벤트를 처리 하는 더 나은 성능을 얻을 수 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>합니다. 이 연습에서는 계층 이벤트와 DTE 이벤트 보여줍니다. 이 절차에서는 공유 프로젝트 및 플랫폼 프로젝트에 이벤트 수신기를 추가 합니다. 그런 다음 공유 프로젝트의 파일 및 플랫폼 프로젝트에서 다른 파일 이름을 바꾸는 경우에 각 이름 바꾸기 작업에 대해 발생 하는 이벤트를 확인할 수 있습니다.  
  
     이 절차에서는 공유 프로젝트 및 플랫폼 프로젝트에 이벤트 수신기를 추가 합니다. 그런 다음 공유 프로젝트의 파일 및 플랫폼 프로젝트에서 다른 파일 이름을 바꾸는 경우에 각 이름 바꾸기 작업에 대해 발생 하는 이벤트를 확인할 수 있습니다.  
  
2.  이벤트 수신기를 추가 합니다. 프로젝트에 새 클래스 파일을 추가 하 고 HierarchyEventListener.cs 호출 합니다.  
  
3.  HierarchyEventListener.cs 파일을 열고 다음 추가 문을 사용 하 여:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell.Interop;  
    using Microsoft.VisualStudio;  
    using System.IO;  
  
    ```  
  
4.  있어야는 `HierarchyEventListener` 클래스 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents>:  
  
    ```csharp  
    class HierarchyEventListener : IVsHierarchyEvents  
    { }  
  
    ```  
  
5.  멤버를 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents>와 같이, 아래 코드입니다.  
  
    ```csharp  
    class HierarchyEventListener : IVsHierarchyEvents  
    {  
        private IVsHierarchy hierarchy;  
        IVsOutputWindowPane output;   
  
        internal HierarchyEventListener(IVsHierarchy hierarchy, IVsOutputWindowPane outputWindow) {  
             this.hierarchy = hierarchy;  
             this.output = outputWindow;  
        }  
  
        int IVsHierarchyEvents.OnInvalidateIcon(IntPtr hIcon) {  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnInvalidateItems(uint itemIDParent) {  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnItemAdded(uint itemIDParent, uint itemIDSiblingPrev, uint itemIDAdded) {  
            output.OutputStringThreadSafe("IVsHierarchyEvents.OnItemAdded: " + itemIDAdded + "\n");  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnItemDeleted(uint itemID) {  
            output.OutputStringThreadSafe("IVsHierarchyEvents.OnItemDeleted: " + itemID + "\n");  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnItemsAppended(uint itemIDParent) {  
            output.OutputStringThreadSafe("IVsHierarchyEvents.OnItemsAppended\n");  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnPropertyChanged(uint itemID, int propID, uint flags) {  
            output.OutputStringThreadSafe("IVsHierarchyEvents.OnPropertyChanged: item ID " + itemID + "\n");  
            return VSConstants.S_OK;  
        }  
    }  
  
    ```  
  
6.  동일한 클래스에서 DTE 이벤트에 대 한 다른 이벤트 처리기를 추가 <xref:EnvDTE.ProjectItemsEventsClass.ItemRenamed>, 프로젝트 항목 이름을 바꿀 때마다 발생 하 합니다.  
  
    ```csharp  
    public void OnItemRenamed(EnvDTE.ProjectItem projItem, string oldName)  
    {  
        output.OutputStringThreadSafe(string.Format("[Event] Renamed {0} to {1} in project {2}\n",  
             oldName, Path.GetFileName(projItem.get_FileNames(1)), projItem.ContainingProject.Name));  
    }  
    ```  
  
7.  계층 이벤트에 등록 합니다. 추적 하는 모든 프로젝트에 대해 별도로 등록 해야 합니다. 에 다음 코드를 추가 `ShowMessageBox`, 공유 프로젝트의 경우 오류 코드 및 기타 플랫폼 프로젝트 중 하나에 대해 하나씩입니다.  
  
    ```csharp  
    // hook up the event listener for hierarchy events on the shared project  
    HierarchyEventListener listener1 = new HierarchyEventListener(sharedHier, output);  
    uint cookie1;  
    sharedHier.AdviseHierarchyEvents(listener1, out cookie1);  
  
    // hook up the event listener for hierarchy events on the   
    active project  
    HierarchyEventListener listener2 = new HierarchyEventListener(activePlatformHier, output);  
    uint cookie2;  
    activePlatformHier.AdviseHierarchyEvents(listener2, out cookie2);  
    ```  
  
8.  DTE 프로젝트 항목 이벤트에 대 한 등록 <xref:EnvDTE.ProjectItemsEventsClass.ItemRenamed>합니다. 두 번째 수신기를 연결 후에 다음 코드를 추가 합니다.  
  
    ```csharp  
    // hook up DTE events for project items  
    Events2 dteEvents = (Events2)dte.Events;  
    dteEvents.ProjectItemsEvents.ItemRenamed += listener1.OnItemRenamed;  
  
    ```  
  
9. 공유 항목을 수정 합니다. 플랫폼 프로젝트;에서 공유 항목을 수정할 수 없습니다. 대신, 이러한 항목의 실제 소유자가 있는 공유 프로젝트에 이미지를 수정할 해야 있습니다. 와 공유 프로젝트에 해당 하는 항목 ID를 가져올 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.IsDocumentInProject%2A>를 공유 하는 항목의 전체 경로 제공 합니다. 그런 다음 공유 항목을 수정할 수 있습니다. 플랫폼 프로젝트 변경 내용을 전파 됩니다.  
  
    > [!IMPORTANT]
    >  프로젝트 항목을 수정 하기 전에 공유 항목 인지 여부를 찾아야 합니다.  
  
     다음 메서드는 프로젝트 항목 파일의 이름을 수정합니다.  
  
    ```csharp  
    private void ModifyFileNameInProject(IVsHierarchy project, string path)  
    {    
        int found;  
        uint projectItemID;  
        VSDOCUMENTPRIORITY[] priority = new VSDOCUMENTPRIORITY[1];  
        if (ErrorHandler.Succeeded(((IVsProject)project).IsDocumentInProject(path, out found, priority, out projectItemID))  
            && found != 0)  
        {  
            var name = DateTime.Now.Ticks.ToString() + Path.GetExtension(path);  
            project.SetProperty(projectItemID, (int)__VSHPROPID.VSHPROPID_EditLabel, name);  
            output.OutputStringThreadSafe(string.Format("Renamed {0} to {1}\n", path,name));  
        }  
    }  
    ```  
  
10. 이 메서드를 다른 코드에서 모든 호출 `ShowMessageBox` 수정 하려면 파일 공유 프로젝트에 항목 이름을 지정 합니다. 이 공유 프로젝트에 항목의 전체 경로 가져오는 코드 뒤에 삽입 합니다.  
  
    ```csharp  
    // change the file name of an item in a shared project  
    this.InspectHierarchyItems(activePlatformHier, (uint)VSConstants.VSITEMID.Root, 1, sharedItemIds, true, true);  
    ErrorHandler.ThrowOnFailure(((IVsProject)activePlatformHier).GetMkDocument(sharedItemId, out fullPath));   
    output.OutputStringThreadSafe(string.Format("Shared project item ID = {0}, full path = {1}\n", sharedItemId, fullPath));  
    this.ModifyFileNameInProject(sharedHier, fullPath);  
    ```  
  
11. 프로젝트를 빌드하고 실행합니다. 실험적 인스턴스에서 C# 유니버설 허브 응용 프로그램을 만들고로 이동는 **도구** 메뉴를 클릭 **호출 TestUniversalProject**, 일반 출력 창에 있는 텍스트를 확인 합니다. 공유에 첫 번째 항목의 이름 (것으로 예상 App.xaml 파일 되도록) 프로젝트를 변경 해야 하며를 확인할는 <xref:EnvDTE.ProjectItemsEventsClass.ItemRenamed> 이벤트가 발생 합니다. 이 경우 App.xaml 이름을 바꾸면도 바꿀 새 이름을 App.xaml.cs, 이후 네 개의 이벤트 (각 플랫폼 프로젝트에 대해 두 개)에 표시 됩니다. (DTE 이벤트 공유 프로젝트에 항목을 추적 하지 않습니다.) 두 개의 표시 되어야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A> 이벤트 (하나씩 각 플랫폼 프로젝트에 대 한)은 아니지만 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemAdded%2A> 이벤트입니다.  
  
12. 이제 플랫폼 프로젝트에서 파일의 이름을 바꾸고를 시도 하 고 발생 하는 이벤트의 차이 확인할 수 있습니다. 에 다음 코드를 추가 `ShowMessageBox` 를 호출한 후 `ModifyFileName`합니다.  
  
    ```csharp  
    // change the file name of an item in a platform project  
    var unsharedItemIds = new List<uint>();  
    this.InspectHierarchyItems(activePlatformHier, (uint)VSConstants.VSITEMID.Root, 1, unsharedItemIds, false, false);  
  
    var unsharedItemId = unsharedItemIds[0];  
    string unsharedPath;  
    ErrorHandler.ThrowOnFailure(((IVsProject)activePlatformHier).GetMkDocument(unsharedItemId, out unsharedPath));  
    output.OutputStringThreadSafe(string.Format("Platform project item ID = {0}, full path = {1}\n", unsharedItemId, unsharedPath));  
  
    this.ModifyFileNameInProject(activePlatformHier, unsharedPath);  
    ```  
  
13. 프로젝트를 빌드하고 실행합니다. 실험적 인스턴스에서 C# 유니버설 프로젝트를 만들고로 이동는 **도구** 메뉴를 클릭 **호출 TestUniversalProject**, 일반 출력 창에 있는 텍스트를 확인 합니다. 모두 표시 됩니다 플랫폼 프로젝트에서 파일의 이름을 바꾸면 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemAdded%2A> 이벤트 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A> 이벤트입니다. 파일에 다른 모든 파일을 변경할 수 인 한 변경 이후 및 없기 때문에 아무 곳 이나 플랫폼 프로젝트의 항목에 대 한 변경 내용을 전파 하지 않습니다, 각이 이벤트 중 하나만 이러한 합니다.