---
title: "프로젝트 파일에서 데이터를 저장합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 파일에 저장 되는 데이터 [Visual Studio]"
  - "프로젝트 파일"
  - "프로젝트 파일, 데이터를 저장 합니다."
ms.assetid: a3d4b15b-a91e-41ba-b235-e62632d11bc5
caps.latest.revision: 28
caps.handback.revision: 28
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로젝트 파일에서 데이터를 저장합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로젝트 하위 저장 한 프로젝트 파일에서 하위 형식의 특정 데이터를 검색할 수 있습니다.  관리 패키지 프레임 워크 \(MPF\)이이 작업을 수행 하는 두 개의 인터페이스를 제공 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> 인터페이스를 허용 하는 속성의 값을 액세스 하는 **MSBuild** 프로젝트 파일의 섹션입니다.  가 제공 하는 방법을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> 모든 사용자가 관련된 데이터를 로드 하거나 저장 하는 사용자 요구를 빌드할 때마다 호출할 수 있습니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> 빌드 자유 형식의 xml 관련된 데이터를 유지 하는 데 사용 됩니다.  가 제공 하는 방법을 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> 라고 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 때마다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트 파일에 빌드 관련된 데이터를 유지 해야 합니다.  
  
 빌드 및 빌드 관련된 데이터를 유지 하는 방법에 대 한 자세한 내용은 참조 하십시오. [MSBuild 프로젝트 파일에 데이터를 유지](../extensibility/internals/persisting-data-in-the-msbuild-project-file.md).  
  
## 관련 데이터를 저장 하 고 빌드를 검색 하는 중  
  
#### 관련 된 프로젝트 파일의 빌드를 저장  
  
-   호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetPropertyValue%2A> 메서드는 프로젝트 파일의 전체 경로 저장 합니다.  
  
    ```  
    private SpecializedProject project;  
    IVsBuildPropertyStorage projectStorage = (IVsBuildPropertyStorage)project;  
    string newFullPath = GetNewFullPath();  
    // Set a full path of the project file.  
    ErrorHandler.ThrowOnFailure(projectStorage.SetPropertyValue(  
        "MSBuildProjectDirectory",  
        String.Empty,  
        (uint)_PersistStorageType.PST_PROJECT_FILE, newFullPath));  
    ```  
  
#### 빌드를 검색 하는 프로젝트 파일에서 데이터 관련  
  
-   호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.GetPropertyValue%2A> 프로젝트 파일의 전체 경로 검색 하는 방법입니다.  
  
    ```  
    private SpecializedProject project;  
    IVsBuildPropertyStorage projectStorage = (IVsBuildPropertyStorage)project;  
    string fullPath;  
    // Get a full path of the project file.  
    ErrorHandler.ThrowOnFailure(projectStorage.GetPropertyValue(  
        "MSBuildProjectDirectory",  
        String.Empty,  
        (uint)_PersistStorageType.PST_PROJECT_FILE, out fullPath));  
    ```  
  
## 저장 및 검색 하는 중 비\-관련된 데이터 빌드  
  
#### 관련 된 프로젝트 파일의 빌드 저장  
  
1.  구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.IsFragmentDirty%2A> 마지막으로 XML 조각을 변경 되었는지 여부를 확인 하는 메서드는 현재 파일에 저장 합니다.  
  
    ```  
    public int IsFragmentDirty(uint storage, out int pfDirty)  
    {  
        pfDirty = 0;  
        switch (storage)  
        {  
            case (uint)_PersistStorageType.PST_PROJECT_FILE:  
            {  
                if (isDirty)  
                    pfDirty |= 1;  
                break;  
            }  
            case (uint)_PersistStorageType.PST_USER_FILE:  
            {  
                // We do not store anything in the user file.  
                break;  
            }  
        }  
  
        // Forward the call to inner flavor(s)   
        if (pfDirty == 0 && innerCfg != null && this.innerCfg is IPersistXMLFragment)  
            return ((IPersistXMLFragment)this.innerCfg).IsFragmentDirty(storage, out pfDirty);  
  
        return VSConstants.S_OK;  
  
    }  
    ```  
  
2.  구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.Save%2A> 프로젝트 파일에 XML 데이터를 저장 하는 방법입니다.  
  
    ```  
    public int Save(ref Guid guidFlavor, uint storage, out string pbstrXMLFragment, int fClearDirty)  
    {  
        pbstrXMLFragment = null;  
  
        if (IsMyFlavorGuid(ref guidFlavor))  
        {  
            switch (storage)  
            {  
                case (uint)_PersistStorageType.PST_PROJECT_FILE:  
                {  
                    // Create XML for our data.  
                    XmlDocument doc = new XmlDocument();  
                    XmlNode root = doc.CreateElement(this.GetType().Name);  
  
                    XmlNode node = doc.CreateElement(targetsTag);  
                    node.AppendChild(doc.CreateTextNode(this.TargetsToExecute));  
                    root.AppendChild(node);  
  
                    node = doc.CreateElement(updateTargetsTag);  
                    node.AppendChild(doc.CreateTextNode(this.UpdateTargetList.ToString()));  
                    root.AppendChild(node);  
  
                    doc.AppendChild(root);  
                    // Get XML fragment representing our data  
                    pbstrXMLFragment = doc.InnerXml;  
  
                    if (fClearDirty != 0)  
                        isDirty = false;  
                    break;  
                }  
                case (uint)_PersistStorageType.PST_USER_FILE:  
                {  
                    // We do not store anything in the user file.  
                    break;  
                }  
            }  
        }  
  
        // Forward the call to inner flavor(s)  
        if (this.innerCfg != null && this.innerCfg is IPersistXMLFragment)  
            return ((IPersistXMLFragment)this.innerCfg).Save(ref guidFlavor, storage, out pbstrXMLFragment, fClearDirty);  
  
        return VSConstants.S_OK;  
    }  
    ```  
  
#### 프로젝트 파일에 빌드 관련된 데이터를 검색 하려면  
  
1.  구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.InitNew%2A> 프로젝트 확장 속성과 다른 빌드에 관계 없이 데이터를 초기화 하는 방법입니다.  프로젝트 파일에 있는 XML 구성 데이터가 없으면이 메서드가 호출 됩니다.  
  
    ```  
    public int InitNew(ref Guid guidFlavor, uint storage)  
    {  
        //Return,if it is our guid.  
        if (IsMyFlavorGuid(ref guidFlavor))  
            return VSConstants.S_OK;  
  
        //Forward the call to inner flavor(s).  
        if (this.innerCfg != null && this.innerCfg is IPersistXMLFragment)  
            return ((IPersistXMLFragment)this.innerCfg).InitNew(ref guidFlavor, storage);  
  
        return VSConstants.S_OK;  
    ```  
  
2.  구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.Load%2A> 프로젝트 파일에서 XML 데이터를 로드 하는 방법입니다.  
  
    ```  
    public int Load(ref Guid guidFlavor, uint storage, string pszXMLFragment)  
    {  
        if (IsMyFlavorGuid(ref guidFlavor))  
        {  
            switch (storage)  
            {  
                case (uint)_PersistStorageType.PST_PROJECT_FILE:  
                {  
                    // Load our data from the XML fragment.  
                    XmlDocument doc = new XmlDocument();  
                    XmlNode node = doc.CreateElement(this.GetType().Name);  
                    node.InnerXml = pszXMLFragment;  
                    if (node == null  
                        || node.FirstChild == null  
                        || node.FirstChild.ChildNodes.Count == 0  
                        || node.FirstChild.ChildNodes[0].Name != targetsTag)  
                        break;  
                    this.TargetsToExecute = node.FirstChild.ChildNodes[0].InnerText;  
  
                    if (node.FirstChild.ChildNodes.Count <= 1  
                        || node.FirstChild.ChildNodes[1].Name != updateTargetsTag)  
                        break;  
                    this.UpdateTargetList = bool.Parse(node.FirstChild.ChildNodes[1].InnerText);  
                    break;  
                }  
                case (uint)_PersistStorageType.PST_USER_FILE:  
                {  
                    // We do not store anything in the user file.  
                    break;  
                }  
            }  
        }  
  
        // Forward the call to inner flavor(s)  
        if (this.innerCfg != null && this.innerCfg is IPersistXMLFragment)  
            return ((IPersistXMLFragment)this.innerCfg).Load(ref guidFlavor, storage, pszXMLFragment);  
  
        return VSConstants.S_OK;  
    }  
    ```  
  
> [!NOTE]
>  이 항목에서 제공 하는 모든 코드 예제는 보다 큰 예제의 일부입니다 [VSSDK 샘플](../misc/vssdk-samples.md).  
  
## 참고 항목  
 [MSBuild 프로젝트 파일에 데이터를 유지](../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)