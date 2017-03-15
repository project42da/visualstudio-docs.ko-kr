---
title: "설정 내보내기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDE, 관리되는 패키지 프레임워크를 사용하여 설정 내보내기"
  - "관리되는 패키지 프레임워크, 환경 설정 내보내기"
  - "사용자 설정[Visual Studio SDK], 관리되는 패키지 프레임워크를 사용하여 내보내기"
  - "IDE 설정, 관리되는 패키지 프레임워크를 사용하여 내보내기"
ms.assetid: cb3ddb38-4e75-4f05-a83a-8396345bc36c
caps.latest.revision: 24
caps.handback.revision: 24
manager: "douge"
---
# 설정 내보내기
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\)을 사용 하 여 구현 하는 클래스는 <xref:Microsoft.VisualStudio.Shell.IProfileManager> 있는 Vspackage의 상태를 저장 하려면 해당된 VSPackage 구현 지원 파일로 등록 된 클래스와 인터페이스 합니다.  
  
 IDE를 구현 하는 클래스를 인스턴스화하고 때문에 <xref:Microsoft.VisualStudio.Shell.IProfileManager> 설정을 지 원하는 인터페이스 <xref:Microsoft.VisualStudio.Shell.IProfileManager> 는 독립적인 클래스에서 구현 해야 합니다.  
  
> [!NOTE]
>  구현 되지 않는 <xref:Microsoft.VisualStudio.Shell.IProfileManager> 을 구현 하는 클래스에서 <xref:Microsoft.VisualStudio.Shell.Package>.  
  
### 내보내기 설정을 구현 하기  
  
1.  구현 하는 클래스를 선언에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설정 합니다.  
  
     로 구현 하는 클래스를 선언에서 <xref:Microsoft.VisualStudio.Shell.IProfileManager> 인터페이스 및 GUID가 제공 됩니다.  
  
    > [!NOTE]
    >  해당 구현 클래스 <xref:Microsoft.VisualStudio.Shell.IProfileManager> 도 구현 해야 <xref:System.ComponentModel.IComponent>.  이 클래스에서 파생 하 여 수행할 수 있습니다 <xref:System.ComponentModel.Component>.  
  
     예를 들면 다음과 같습니다.  
  
    ```  
    [Guid("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")]  
    internal class MyPackageProfileManager : Component, IProfileManager   
    ```  
  
2.  설정을 구현 하는 클래스에서 올바른 상태 정보를 얻는 지 확인 하십시오.  이 절차는 각 Vspackage를 한정 되며 상태에서 자동화를 얻는, 레지스트리 키를 쿼리 또는 쿼리 있는 VSPackage 포함 될 수 있습니다.  
  
     일반적으로 다음 예제와 같이 구현을 사용은 <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> 메서드를 확인 하 고 VSPackage 상태 정보를 준비 합니다.  
  
    > [!NOTE]
    >  <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> 메서드는 호출할 IDE에서 지 원하는 VSPackage 초기화 될 때.  
  
     이 경우에 구현은 <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> 메서드는 이러한 작업을 수행 합니다.  
  
    -   구성 정보가 레지스트리에 저장 된 및 VSPackage 현재 구성에서 상태 정보 액세스를 얻습니다.  
  
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
  
    -   반환 된 값에 따라 해당 `MakeCurrentSettingTheDefault` 메서드는 VSPackage 중 업데이트 레지스트리 설정 레지스트리 설정을 사용 하 여 현재 VSPackage 상태 또는 상태를 사용 하 여.  
  
        ```vb#  
        If mySvc.MyPackage.MakeCurrentSettingTheDefault() Then   
            DirectCast(mySvc.MyPackage.packageState, IComPropertyBrowser).SaveState(pbrsKey)   
        Else   
            DirectCast(mySvc.MyPackage.packageState, IComPropertyBrowser).LoadState(pbrsKey)   
        End If  
        ```  
  
        ```c#  
        if (mySvc.MyPackage.MakeCurrentSettingTheDefault()){  
          ((IComPropertyBrowser)mySvc.MyPackage.packageState).SaveState(pbrsKey);  
        }else{  
          ((IComPropertyBrowser)mySvc.MyPackage.packageState).LoadState(pbrsKey);  
        }  
        ```  
  
         이 예제에서는 단순화를 위해 하지 않으면는 `MakeCurrentSettingsTheDefault` 메서드가 반환 `true`, 항상 레지스트리에 저장 되어 기본 현재 상태를 다시 설정 합니다.  
  
3.  설정을 구현 하는 클래스도 디스크 상태로 유지 되도록 해야 합니다.  
  
     상태 정보를 설정 디스크 파일의 실제 쓰기의 클래스 구현에서 항상 수행 해야는 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToXml%2A> 메서드.  설정 작성기 작업의 구체적인 구현에 따라 달라 집니다.  
  
     그러나 클래스 상태 정보에 액세스 해야 하 고는 제공 된 사용 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsWriter> 인터페이스 데이터 설정을 파일에 저장 합니다.  
  
     구현은 다음 예제에서와 같이 일반적으로 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToXml%2A> 메서드 상태 정보를 확인 하지 않습니다.  유효성 검사가 수행 됩니다 있는 <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> 메서드가 있습니다.  대신 구현 단순히 상태 정보에 액세스 하 여,이 경우 문자열 데이터로 씁니다.  
  
    ```vb#  
    Dim mySvc As MyPackageService = TryCast(GetService(GetType(MyPackage)), MyPackageService)   
    If mySvc IsNot Nothing Then   
        ' Information is stored in a StateObject   
        Dim myState As StateObject = mySvc.MyPackage.packageState   
        writer.WriteSettingString("PbrsAlpha", (If(myState.SortState = SortState.Alphabetical, "1", "0")))   
        writer.WriteSettingString("PbrsShowDesc", (If(myState.HelpVisible, "1", "0")))   
    End If  
  
    ```  
  
    ```c#  
    MyPackageService mySvc = GetService(typeof(MyPackage)) as MyPackageService;  
    if (mySvc != null) {  
      // Information is stored in a StateObject  
      StateObject myState = mySvc.MyPackage.packageState;  
     writer.WriteSettingString(   
                                "PbrsAlpha",   
                                (myState.SortState == SortState.Alphabetical ? "1" : "0"));  
      writer.WriteSettingString(   
                                "PbrsShowDesc",   
                                (myState.HelpVisible ? "1" : "0"));  
    }  
    ```  
  
     구현 세부 사항은 다음과 같습니다.  
  
    -   명시적으로 작성 하 고 투명 하 게 데이터를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ExportSettings%2A> 메서드 구현을 설정 API 또한 저장 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전 정보입니다.  따라서, 저장 된 설정 버전 설정을 가져올 때 생성 되는 IDE에 대해 비교할 수 있습니다.  
  
    -   값은 `pszSettingName` 의 메서드에 제공 된 인수를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsWriter> 인터페이스 설정 범주에 저장 된 각 데이터 요소의 고유 하 게 식별 해야 합니다.  
  
        > [!NOTE]
        >  이름은 구현 하는 클래스의 범위 내에서 고유 해야 합니다.  IDE의 값과 설정이 구현 하는 클래스의 GUID를 사용 하 여 `pszSettingName` 저장는 각 설정을 식별 합니다.  두 개 이상의 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsWriter> 같은 메서드 `pszSettingName` 값 이라고, 설정 파일에 원래 값을 덮어씁니다.  
  
    -   순서를 읽기 및 쓰기 작업이 중요 하므로 설정 파일 임의 데이터 액세스를 지원 합니다.  기록기 연산이 구현에서는 다음 예제에서 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToXml%2A> 메서드는 반대 읽기 작업에 <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromXml%2A> 메서드.  
  
    -   구현이 지원 되는 네 가지 형식 중 하나에 데이터를 매핑할 수 있습니다 경우 다음 방법에는 제한이 훨씬 또는 어떤 형식의 데이터를 쓸 수 있습니다.  
  
        > [!NOTE]
        >  노동 사이의 분할은 <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> 및 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToXml%2A> 메서드 구현에 따라 다릅니다 및 약간 임의적입니다.  다시 예를 들어, 구현의 빈 구현을 사용 하 여 작성할 수 있습니다 해당 <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> 메서드 및 모든 레지스트리 및 상태 쿼리 수행 하도록 하 여는 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToXml%2A> 메서드.  
  
4.  있는 Vspackage를 지원을 제공 하는 클래스를 구현 하는 설정을 등록 합니다.  
  
     인스턴스를 적용 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 되는 생성을 사용 하 여는 <xref:System.Type> 구현 하는 클래스의 <xref:Microsoft.VisualStudio.Shell.IProfileManager> 에 있는 VSPackage <xref:Microsoft.VisualStudio.Shell.Package> 구현 합니다.  
  
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
  
     이 경우 IDE 특성을 알리는는 `MyPackageProfileManager` 클래스를 제공 하는 설정을 구현 하는 `MyPackage` 클래스입니다.  사용자 지정 설정을 지점이 레지스트리의 hklm\\software\\microsoft\\visualstudio\\에서 만들어진*버전*\\UserSettings\\ CoreUI\_MyPackage, 어디  *버전* 의 버전입니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 예를 들어, 10.0.  
  
     자세한 내용은 [사용자 설정에 대 한 지원](../extensibility/internals/support-for-user-settings.md) 및 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute>을 참조하십시오.  
  
## 예제  
 다음 예제에서는 구현 <xref:Microsoft.VisualStudio.Shell.IProfileManager> 클래스입니다.  
  
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
            ' First, check if data is obtained from the correct major version   
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
  
Convert C# to VB.NET  
  
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
      // First, check if data is obtained from the correct major version   
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
 [설정 가져오기](../misc/importing-settings.md)   
 [사용자 설정에 대 한 지원](../extensibility/internals/support-for-user-settings.md)