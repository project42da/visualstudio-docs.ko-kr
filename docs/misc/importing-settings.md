---
title: "설정 가져오기 | Microsoft Docs"
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
  - "사용자 설정[Visual Studio SDK], 관리되는 패키지 프레임워크를 사용하여 가져오기"
  - "IDE 설정, 관리되는 패키지 프레임워크를 사용하여 가져오기"
  - "IDE, 관리되는 패키지 프레임워크를 사용하여 설정 가져오기"
  - "관리되는 패키지 프레임워크, 환경 설정 가져오기"
ms.assetid: 943f9a5b-c5a5-45ce-a5a9-8d4c02f15577
caps.latest.revision: 23
caps.handback.revision: 23
manager: "douge"
---
# 설정 가져오기
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE\(통합 개발 환경\)에서는 <xref:Microsoft.VisualStudio.Shell.IProfileManager> 인터페이스를 구현하며 VSPackage 구현을 지원하도록 등록되는 클래스를 사용합니다. 이 구현은 VSPackage의 상태를 검색하는 데 사용됩니다.  
  
 IDE는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설정을 지원하기 위해 <xref:Microsoft.VisualStudio.Shell.IProfileManager> 인터페이스를 구현하는 클래스를 인스턴스화하므로 <xref:Microsoft.VisualStudio.Shell.IProfileManager> 인터페이스는 독립 클래스에서 구현되어야 합니다.  
  
> [!NOTE]
>  <xref:Microsoft.VisualStudio.Shell.Package>를 구현하는 클래스에서 <xref:Microsoft.VisualStudio.Shell.IProfileManager>를 구현하지 마세요.  
  
### 설정 내보내기를 구현하려면  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설정을 구현하는 클래스를 선언합니다.  
  
     <xref:Microsoft.VisualStudio.Shell.IProfileManager> 구현으로 클래스를 선언하고 여기에 `GUID`를 제공합니다.  
  
    > [!NOTE]
    >  <xref:Microsoft.VisualStudio.Shell.IProfileManager> 인터페이스를 구현하는 클래스는 <xref:System.ComponentModel.IComponent>를 구현해야 하며 이 작업은 <xref:System.ComponentModel.Component> 클래스에서 클래스를 파생하여 수행할 수도 있습니다.  
  
     예:  
  
    ```  
    [Guid("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")]  
    internal class MyPackageProfileManager : Component, IProfileManager   
    ```  
  
2.  설정을 구현하는 클래스가 디스크에서 상태 데이터를 검색하도록 합니다.  
  
     이 단계는 <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromXml%2A> 메서드를 구현하여 수행합니다.  
  
     유지할 정확한 정보와 이 정보를 VSPackage에서 가져오고 마샬링하는 방법은 각 VSPackage마다 다릅니다.  
  
     VSPackage에서 유지할 정보에 관계없이 <xref:Microsoft.VisualStudio.Shell.IProfileManager>를 구현하는 클래스는 제공된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader> 인터페이스를 사용하여 설정 파일에서 데이터를 검색해야 합니다.  
  
     일반적으로 아래 예제와 같이 <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromXml%2A>도 검색된 데이터를 확인하고 VSPackage의 상태를 업데이트합니다.  
  
    ```vb#  
    Dim mySvc As MyPackageService = TryCast(GetService(GetType(IVSMDMyPackage)), MyPackageService)   
    If mySvc IsNot Nothing Then   
        Dim value As String   
        Dim myState As StateObject = mySvc.MyPackage.packageState   
        reader.ReadSettingString("PbrsShowDesc", value)   
        If value Is Nothing OrElse value = "" Then   
            reader.ReportError("Unable to Help Visibility Setting")   
        Else   
            myState.HelpVisible = Not value.Equals("0")   
        End If   
        reader.ReadSettingString("PbrsAlpha", value)   
        If value Is Nothing OrElse value = "" Then   
            reader.ReportError("Unable to Retrieve Sort Value")   
        Else   
            If Not value.Equals("0") Then   
                myState.SortState = SortState.Alphabetical   
            Else   
                myState.SortState = SortState.Categorized   
            End If   
        End If   
    End If  
    ```  
  
    ```c#  
    MyPackageService mySvc = GetService(typeof(IVSMDMyPackage)) as MyPackageService;  
    if (mySvc != null){  
      string value;  
      StateObject myState = mySvc.MyPackage.packageState;  
      reader.ReadSettingString("PbrsShowDesc", out value);  
      if (value == null || value == ""){  
          reader.ReportError("Unable to Help Visibility Setting");  
      }else{  
          myState.HelpVisible = !value.Equals("0");  
      }  
      reader.ReadSettingString("PbrsAlpha", out value);  
      if (value == null || value == ""){  
          reader.ReportError("Unable to Retrieve Sort Value");  
      }else{  
        if (!value.Equals("0")){  
          myState.SortState = SortState.Alphabetical;  
        }else{  
          myState.SortState = SortState.Categorized;  
        }  
      }  
    }  
    ```  
  
     구현 세부 정보:  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader> 인터페이스의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader.ReportError%2A> 메서드를 사용하여 IDE를 통해 사용자에게 오류를 대화식으로 다시 보고합니다.  
  
        ```vb#  
        reader.ReadSettingString("PbrsAlpha", value)   
        If value Is Nothing OrElse value = "" Then   
            reader.ReportError("Unable to Retrieve Sort Value")   
        End If  
        ```  
  
        ```c#  
          reader.ReadSettingString("PbrsAlpha", out value);  
          if (value == null || value == ""){  
              reader.ReportError("Unable to Retrieve Sort Value");  
          }  
        ```  
  
    -   <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromXml%2A> 메서드 구현은 저장된 설정을 실제 검색하기 전에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader.ReadFileVersion%2A> 메서드를 사용하여 저장된 설정을 내보내는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 버전이 지원되는지 확인합니다.  
  
         아래 예의 경우 구현은 주 버전 번호가 `m_supportVer`인 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전에서 설정이 생성되었는지 확인하여 그렇지 않은 경우에 오류를 표시합니다.  
  
        ```vb#  
        If pnMajor <> m_supportVer Then   
            reader.ReportError("Unsupported Version")   
        End If  
        ```  
  
        ```c#  
        if (pnMajor != m_supportVer){  
          reader.ReportError("Unsupported Version");  
        }  
        ```  
  
    -   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설정 파일은 임의 데이터 액세스를 지원하므로 설정 읽기 및 쓰기 작업의 순서는 중요하지 않습니다. 아래 예에서 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToXml%2A> 메서드 구현의 쓰기 작업 순서는 <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromXml%2A> 메서드의 읽기 작업과 반대입니다.  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsWriter> 인터페이스의 메서드에 제공된 `pszSettingName` 인수의 값은 설정 범주 내에 저장된 각 데이터 요소를 고유하게 식별해야 합니다.  
  
        > [!NOTE]
        >  IDE는 설정을 구현하는 클래스의 GUID와 `pszSettingName`의 값을 사용하여 저장된 각 설정을 식별하므로 이름은 구현 클래스의 범위 내에서만 고유해야 합니다.`pszSettingName` 값이 동일한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsWriter> 메서드를 둘 이상 호출한 경우 설정 파일의 원래 값을 덮어씁니다.  
  
3.  VSPackage 상태와 로컬에 저장 또는 캐시된 설정 간의 일관성을 확인합니다.  
  
     이 단계는 일반적으로 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> 메서드를 구현하는 동안 수행됩니다\(아래 예에서처럼\). 이 단계의 세부 사항은 VSPackage에 따라 다르며 자동화에서 VSPackage의 상태를 가져오고 VSPackage를 쿼리하고 레지스트리 키를 설정하는 과정이 포함될 수 있습니다.  
  
    > [!NOTE]
    >  <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> 메서드는 지원하는 VSPackage의 초기화 도중 IDE가 <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> 메서드를 호출할 때 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> 메서드가 저장한 정보를 검색해야 합니다.  
  
     아래 예에서 설정 지원을 제공하는 클래스는 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> 메서드를 구현하여 다음을 수행합니다.  
  
    -   VSPackage의 업데이트된 상태 정보에 대한 액세스를 얻습니다.  
  
        ```vb#  
        Dim mySvc As MyPackageService = TryCast(GetService(GetType(IVSMDMyPackage)), MyPackageService)   
        Dim package As Package = TryCast(GetService(GetType(Package)), Package)   
        Dim rootKey As RegistryKey = package.UserRegistryRoot  
        ```  
  
        ```c#  
        MyPackageService mySvc = GetService(typeof(IVSMDMyPackage)) as MyPackageService;  
        Package package = GetService(typeof(Package)) as Package;  
        RegistryKey rootKey = package.UserRegistryRoot;  
        ```  
  
    -   이 정보를 사용하여 VSPackage의 레지스트리 설정을 업데이트합니다.  
  
        ```vb#  
        If mySvc.MyPackage.packageState IsNot Nothing Then   
            Using rootKey   
                Using pbrsKey As RegistryKey = rootKey.CreateSubKey(Me.[GetType]().Name)   
                    Using pbrsKey   
                        DirectCast(mySvc.MyPackage.packageState, IComPropertyBrowser).SaveState(pbrsKey)   
                    End Using   
                End Using   
            End Using   
        End If  
        ```  
  
        ```c#  
        if (mySvc.MyPackage.packageState != null) {  
          using (rootKey) {  
            using(RegistryKey pbrsKey = rootKey.CreateSubKey(this.GetType().Name)) {  
              using (pbrsKey) {  
                ((IComPropertyBrowser)mySvc.MyPackage.packageState).SaveState(pbrsKey);  
              }  
            }  
          }  
        }  
        ```  
  
    -   > [!NOTE]
        >  <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromXml%2A> 및 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> 메서드 간의 분업은 구현에 따라 다르며 다소 임의적입니다. 예를 들어 구현이 <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> 메서드의 빈 구현으로 재작성되고 모든 레지스트 및 상태 쿼리가 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToXml%2A> 메서드에서 수행될 수 있습니다.  
  
4.  설정을 VSPackage에 대한 지원 제공으로 구현하는 클래스를 등록합니다.  
  
     VSPackage의 <xref:Microsoft.VisualStudio.Shell.Package> 구현에 <xref:Microsoft.VisualStudio.Shell.IProfileManager>를 구현하는 클래스의 <xref:System.Type>를 사용하여 생성된 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute>의 인스턴스를 적용합니다.  
  
    ```vb#  
    <ProvideProfile(GetType(MyPackageProfileManager), "CoreUI", "MyPackage", 1004, 1004, False)> _   
    <Guid("YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY")> _   
    Class MyPackage   
        Inherits Package   
    End Class  
    ```  
  
    ```c#  
     [ProvideProfile(typeof(MyPackageProfileManager), "CoreUI", "MyPackage", 1004, 1004, false)]  
    [Guid("YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY")]  
    class MyPackage: Package   
    ```  
  
     이 경우 특성을 `MyPackageProfileManager` 클래스가 `MyPackage` 클래스에 설정 구현을 제공한다는 것을 IDE에 알립니다. 레지스트리의 사용자 지정 설정점은 HKLM\\Software\\Microsoft\\VisualStudio\\*\<Version\>*\\UserSettings\\ CoreUI\_MyPackage\(여기서 *\<Version\>*은 8.0과 같은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 버전\) 아래에 만들어집니다.  
  
     자세한 내용은 [사용자 설정에 대 한 지원](../extensibility/internals/support-for-user-settings.md) 및 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute>을 참조하십시오.  
  
## 예제  
 다음 예에서는 클래스에서 <xref:Microsoft.VisualStudio.Shell.IProfileManager>를 구현합니다.  
  
```vb#  
Imports System   
Imports System.Runtime.InteropServices   
Imports Microsoft.VisualStudio.Shell   
Imports Microsoft.VisualStudio.Shell.Interop   
Imports Microsoft.Win32   
Imports myPackageNameSpace   
Namespace myProfileManagerNameSpace  
  
    <Guid("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")> _   
    Friend Class MyPackageProfileManager   
        Inherits System.ComponentModel.Component   
        Implements IProfileManager   
        Friend Const m_supportVer As Integer = 8   
        Public Sub SaveSettingsToXml(ByVal writer As IVsSettingsWriter)   
            Dim mySvc As MyPackageService = TryCast(GetService(GetType(MyPackage)), MyPackageService)   
            If mySvc IsNot Nothing Then   
                ' Information is stored in a StateObject.   
                Dim myState As StateObject = mySvc.MyPackage.packageState   
                writer.WriteSettingString("PbrsAlpha", (If(myState.SortState = SortState.Alphabetical, "1", "0")))   
                writer.WriteSettingString("PbrsShowDesc", (If(myState.HelpVisible, "1", "0")))   
            End If   
        End Sub   
  
        Public Sub LoadSettingsFromXml(ByVal reader As IVsSettingsReader)   
  
            Dim pnMajor As Integer, pnMinor As Integer, pnBuild As Integer   
            ' First check if we are getting data from the correct major version.   
            reader.ReadVersion(pnMajor, pnMinor, pnBuild)   
            If pnMajor <> m_supportVer Then   
                reader.ReportError("Unsupported Version")   
            Else   
                Dim mySvc As MyPackageService = TryCast(GetService(GetType(IVSMDMyPackage)), MyPackageService)   
                If mySvc IsNot Nothing Then   
                    Dim value As String   
                    Dim myState As StateObject = mySvc.MyPackage.packageState   
                    reader.ReadSettingString("PbrsShowDesc", value)   
                    ' Not all values must be present.   
                    If value Is Nothing OrElse value = "" Then   
                        reader.ReportError("Unable to Help Visibility Setting")   
                    Else   
                        myState.HelpVisible = Not value.Equals("0")   
                    End If   
                    reader.ReadSettingString("PbrsAlpha", value)   
                    ' Not all values must be present.   
                    If value Is Nothing OrElse value = "" Then   
                        reader.ReportError("Unable to Retrieve Sort Value")   
                    Else   
                        If Not value.Equals("0") Then   
                            myState.SortState = SortState.Alphabetical   
                        Else   
                            myState.SortState = SortState.Categorized   
                        End If   
                    End If   
                End If   
            End If   
        End Sub   
  
        Public Sub SaveSettingsToStorage()   
            Dim mySvc As MyPackageService = TryCast(GetService(GetType(IVSMDMyPackage)), MyPackageService)   
            Dim package As Package = TryCast(GetService(GetType(Package)), Package)   
            Dim rootKey As RegistryKey = package.UserRegistryRoot   
  
            If mySvc.MyPackage.packageState IsNot Nothing Then   
                Using rootKey   
                    Using pbrsKey As RegistryKey = rootKey.CreateSubKey(Me.[GetType]().Name)   
                        Using pbrsKey   
                            DirectCast(mySvc.MyPackage.packageState, IComPropertyBrowser).SaveState(pbrsKey)   
                        End Using   
                    End Using   
                End Using   
            End If   
        End Sub   
  
        Public Sub LoadSettingsFromStorage()   
            Dim mySvc As MyPackageService = TryCast(GetService(GetType(IVSMDMyPackage)), MyPackageService)   
            Dim package As Package = TryCast(GetService(GetType(Package)), Package)   
            Dim rootKey As RegistryKey = package.UserRegistryRoot   
            Using rootKey   
                Dim pbrsKey As RegistryKey = rootKey.OpenSubKey(Me.[GetType]().Name)   
                If pbrsKey IsNot Nothing Then   
                    Using pbrsKey   
                        If mySvc.MyPackage.MakeCurrentSettingTheDefault() Then   
                            DirectCast(mySvc.MyPackage.packageState, IComPropertyBrowser).SaveState(pbrsKey)   
                        Else   
                            DirectCast(mySvc.MyPackage.packageState, IComPropertyBrowser).LoadState(pbrsKey)   
                        End If   
                    End Using   
                End If   
            End Using   
        End Sub   
    End Class   
End Namespace  
  
```  
  
```c#  
namespace myProfileManagerNameSpace  {  
  
  using System;  
  using System.Runtime.InteropServices;  
  using Microsoft.VisualStudio.Shell;  
  using Microsoft.VisualStudio.Shell.Interop;  
  using Microsoft.Win32;  
  using myPackageNameSpace;  
  
  [Guid("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")]  
  internal class MyPackageProfileManager : System.ComponentModel.Component , IProfileManager {  
    internal const int m_supportVer = 8;  
    public void SaveSettingsToXml(IVsSettingsWriter writer) {  
      MyPackageService mySvc = GetService(typeof(MyPackage)) as MyPackageService;  
      if (mySvc != null) {  
        // Information is stored in a StateObject.  
        StateObject myState = mySvc.MyPackage.packageState;  
        writer.WriteSettingString(   
                                  "PbrsAlpha",   
                                  (myState.SortState == SortState.Alphabetical ? "1" : "0"));  
        writer.WriteSettingString(   
                                  "PbrsShowDesc",   
                                  (myState.HelpVisible ? "1" : "0"));  
      }  
    }  
  
    public void LoadSettingsFromXml(IVsSettingsReader reader)  
    {  
  
      int pnMajor, pnMinor, pnBuild;  
      // First check if we are getting data from the correct major version.   
      reader.ReadVersion(pnMajor, pnMinor, pnBuild);  
      if (pnMajor != m_supportVer){  
        reader.ReportError("Unsupported Version");  
      }else{  
        MyPackageService mySvc = GetService(typeof(IVSMDMyPackage)) as MyPackageService;  
        if (mySvc != null){  
          string value;  
          StateObject myState = mySvc.MyPackage.packageState;  
          reader.ReadSettingString("PbrsShowDesc", out value);  
          // Not all values must be present.  
          if (value == null || value == ""){  
              reader.ReportError("Unable to Help Visibility Setting");  
          }else{  
            myState.HelpVisible = !value.Equals("0");  
          }  
          reader.ReadSettingString("PbrsAlpha", out value);  
          // Not all values must be present.  
          if (value == null || value == ""){  
              reader.ReportError("Unable to Retrieve Sort Value");  
          }else{  
            if (!value.Equals("0")){  
              myState.SortState = SortState.Alphabetical;  
            }else{  
              myState.SortState = SortState.Categorized;  
            }  
          }  
        }  
      }  
    }  
  
    public void SaveSettingsToStorage() {  
      MyPackageService mySvc = GetService(typeof(IVSMDMyPackage)) as MyPackageService;  
      Package package = GetService(typeof(Package)) as Package;  
      RegistryKey rootKey = package.UserRegistryRoot;  
  
      if (mySvc.MyPackage.packageState != null) {  
        using (rootKey) {  
          using(RegistryKey pbrsKey = rootKey.CreateSubKey(this.GetType().Name)) {  
            using (pbrsKey) {  
              ((IComPropertyBrowser)mySvc.MyPackage.packageState).SaveState(pbrsKey);  
            }  
          }  
        }  
      }  
    }  
  
    public void LoadSettingsFromStorage() {  
      MyPackageService mySvc = GetService(typeof(IVSMDMyPackage)) as MyPackageService;  
      Package package = GetService(typeof(Package)) as Package;  
      RegistryKey rootKey = package.UserRegistryRoot;  
      using (rootKey) {  
        RegistryKey pbrsKey = rootKey.OpenSubKey(this.GetType().Name);  
        if (pbrsKey != null) {  
          using (pbrsKey) {  
            if (mySvc.MyPackage.MakeCurrentSettingTheDefault()){  
              ((IComPropertyBrowser)mySvc.MyPackage.packageState).SaveState(pbrsKey);  
            }else{  
              ((IComPropertyBrowser)mySvc.MyPackage.packageState).LoadState(pbrsKey);  
            }  
          }  
        }  
      }  
    }  
  }  
}  
```  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.IProfileManager>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsWriter>   
 [설정 내보내기](../misc/exporting-settings.md)   
 [사용자 설정에 대 한 지원](../extensibility/internals/support-for-user-settings.md)