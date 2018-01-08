---
title: "솔루션 탐색기 필터를 확장 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Solution Explorer, extending
- extensibility [Visual Studio], projects and solutions
ms.assetid: df976c76-27ec-4f00-ab6d-a26a745dc6c7
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: afcaef724b5fc5f8270e5126e91d421f2e15b946
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-solution-explorer-filter"></a>솔루션 탐색기 필터를 확장합니다.
확장할 수 **솔루션 탐색기** 필터링 기능을 표시 하거나 서로 다른 파일을 숨깁니다. 예를 들어 C# 클래스 팩터리의 파일만 표시 하는 필터를 만들 수 있습니다는 **솔루션 탐색기**이 연습에서 보여 주듯이, 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
### <a name="create-a-visual-studio-package-project"></a>Visual Studio 패키지 프로젝트 만들기  
  
1.  라는 VSIX 프로젝트 `FileFilter`합니다. 명명 된 사용자 지정 명령 항목 템플릿을 추가 **FileFilter**합니다. 자세한 내용은 참조 [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
2.  에 대 한 참조를 추가 `System.ComponentModel.Composition` 및 `Microsoft.VisualStudio.Utilities`합니다.  
  
3.  만들기 메뉴 명령에 표시 된 **솔루션 탐색기** 도구 모음입니다. FileFilterPackage.vsct 파일을 엽니다.  
  
4.  변경 된 `<Button>` 다음과 블록:  
  
    ```xml  
    <Button guid="guidFileFilterPackageCmdSet" id="FileFilterId" priority="0x0400" type="Button">  
        <Parent guid="guidSHLMainMenu" id="IDG_VS_TOOLBAR_PROJWIN_FILTERS" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>FileNameFilter</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
### <a name="update-the-manifest-file"></a>매니페스트 파일 업데이트  
  
1.  Source.extension.vsixmanifest 파일에서 MEF 구성 된 자산을 추가 합니다.  
  
2.  에 **자산** 탭, 선택는 **새로** 단추입니다.  
  
3.  에 **형식** 필드에서 선택 **Microsoft.VisualStudio.MefComponent**합니다.  
  
4.  에 **소스** 필드에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
5.  에 **프로젝트** 필드를 선택 **FileFilter**를 선택한 후는 **확인** 단추입니다.  
  
### <a name="add-the-filter-code"></a>필터 코드를 추가 합니다.  
  
1.  일부 Guid FileFilterPackageGuids.cs 파일에 추가 합니다.  
  
    ```csharp  
    public const string guidFileFilterPackageCmdSetString = "00000000-0000-0000-0000-00000000"; // get your GUID from the .vsct file  
    public const int FileFilterId = 0x100;  
    ```  
  
2.  FileNameFilter.cs FileFilter 프로젝트에 클래스 파일을 추가 합니다.  
  
3.  빈 네임 스페이스와 빈 클래스 아래 코드로 바꿉니다.  
  
     `Task<IReadOnlyObservableSet> GetIncludedItemsAsync(IEnumerable<IVsHierarchyItem rootItems)` 메서드는 솔루션의 루트를 포함 하는 컬렉션 (`rootItems`) 필터에 포함할 항목의 컬렉션을 반환 합니다.  
  
     `ShouldIncludeInFilter` 에 항목을 필터링 하는 메서드는 **솔루션 탐색기** 지정한 조건을 사용 하 여 기반 계층입니다.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ComponentModel.Composition;  
    using System.Text.RegularExpressions;  
    using System.Threading.Tasks;  
    using Microsoft.Internal.VisualStudio.PlatformUI;  
    using Microsoft.VisualStudio.Shell;  
  
    namespace FileFilter  
    {  
        // Implements ISolutionTreeFilterProvider. The SolutionTreeFilterProvider attribute declares it as a MEF component  
        [SolutionTreeFilterProvider(FileFilterPackageGuids.guidFileFilterPackageCmdSetString, (uint)(FileFilterPackageGuids.FileFilterId))]  
        public sealed class FileNameFilterProvider : HierarchyTreeFilterProvider  
        {  
            SVsServiceProvider svcProvider;  
            IVsHierarchyItemCollectionProvider hierarchyCollectionProvider;  
  
            // Constructor required for MEF composition  
            [ImportingConstructor]  
            public FileNameFilterProvider(SVsServiceProvider serviceProvider, IVsHierarchyItemCollectionProvider hierarchyCollectionProvider)  
            {  
                this.svcProvider = serviceProvider;  
                this.hierarchyCollectionProvider = hierarchyCollectionProvider;  
            }  
  
            // Returns an instance of Create filter class.  
            protected override HierarchyTreeFilter CreateFilter()  
            {  
                return new FileNameFilter(this.svcProvider, this.hierarchyCollectionProvider, FileNamePattern);  
            }  
  
            // Regex pattern for CSharp factory classes  
            private const string FileNamePattern = @"\w*factory\w*(.cs$)";  
  
            // Implementation of file filtering  
            private sealed class FileNameFilter : HierarchyTreeFilter  
            {  
                private readonly Regex regexp;  
                private readonly IServiceProvider svcProvider;  
                private readonly IVsHierarchyItemCollectionProvider hierarchyCollectionProvider;  
  
                public FileNameFilter(  
                    IServiceProvider serviceProvider,  
                    IVsHierarchyItemCollectionProvider hierarchyCollectionProvider,  
                    string fileNamePattern)  
                {  
                    this.svcProvider = serviceProvider;  
                    this.hierarchyCollectionProvider = hierarchyCollectionProvider;  
                    this.regexp = new Regex(fileNamePattern, RegexOptions.IgnoreCase);  
                }  
  
                // Gets the items to be included from this filter provider.   
                // rootItems is a collection that contains the root of your solution  
                // Returns a collection of items to be included as part of the filter  
                protected override async Task<IReadOnlyObservableSet> GetIncludedItemsAsync(IEnumerable<IVsHierarchyItem> rootItems)  
                {  
                    IVsHierarchyItem root = HierarchyUtilities.FindCommonAncestor(rootItems);  
                    IReadOnlyObservableSet<IVsHierarchyItem> sourceItems;  
                    sourceItems = await hierarchyCollectionProvider.GetDescendantsAsync(  
                                        root.HierarchyIdentity.NestedHierarchy,  
                                        CancellationToken);  
  
                    IFilteredHierarchyItemSet includedItems = await hierarchyCollectionProvider.GetFilteredHierarchyItemsAsync(  
                        sourceItems,  
                        ShouldIncludeInFilter,  
                        CancellationToken);  
                    return includedItems;  
                }  
  
                // Returns true if filters hierarchy item name for given filter; otherwise, false</returns>  
                private bool ShouldIncludeInFilter(IVsHierarchyItem hierarchyItem)  
                {  
                    if (hierarchyItem == null)  
                    {  
                        return false;  
                    }  
                    return this.regexp.IsMatch(hierarchyItem.Text);  
                }  
            }  
        }  
    }  
  
    ```  
  
4.  FileFilter.cs, FileFilter 생성자에서 명령 배치 및 처리 코드를 제거 합니다. 결과 다음과 같이 표시 됩니다.  
  
    ```csharp  
    private FileFilter(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException("package");  
        }  
  
        this.package = package;  
    }  
    ```  
  
     ShowMessageBox() 방법을를 제거 합니다.  
  
5.  FileFilterPackage, cs에서 initialize () 메서드의 코드를 다음으로 바꿉니다.  
  
    ```csharp  
    protected override void Initialize()  
    {  
        Debug.WriteLine (string.Format(CultureInfo.CurrentCulture, "Entering Initialize() of: {0}", this.ToString()));  
        base.Initialize();  
    }  
    ```  
  
### <a name="test-your-code"></a>코드 테스트  
  
1.  프로젝트를 빌드하고 실행합니다. 두 번째 Visual Studio 인스턴스가 표시됩니다. 이 실험적 인스턴스에서 이라고 합니다.  
  
2.  Visual Studio의 실험적 인스턴스에서 C# 프로젝트를 엽니다.  
  
3.  솔루션 탐색기 도구 모음 추가 단추를 찾습니다. 왼쪽에서 네 번째 단추가 있어야 합니다.  
  
4.  단추를 클릭할 때 모든 파일을 필터링 해야 하 고 "모든 항목이 필터링 된 보기에서." 나타납니다. 솔루션 탐색기.