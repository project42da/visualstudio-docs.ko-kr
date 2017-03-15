---
title: "레거시 코드 편집기로 조정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-어댑터"
ms.assetid: a208d38e-9bea-41c9-9fe2-38bd86a359cb
caps.latest.revision: 25
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 25
---
# 레거시 코드 편집기로 조정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 편집기에는 기존 코드 구성 요소에서 액세스할 수 있는 많은 기능이 있습니다. 다음 지침에는 편집기 기능을 사용 하기를 VSPackage 예를 들어 비 MEF 구성 요소를 조정 하는 방법을 보여 줍니다. 지침에는 서비스를 가져옵니다 편집기의 관리 및 비관리 코드에서 어댑터를 사용 하는 방법을 보여 줍니다.  
  
## 편집기 어댑터  
 편집기 어댑터 또는, shim은 또한 클래스와 인터페이스를 노출 하는 편집기 개체에 대 한 래퍼는 <xref:Microsoft.VisualStudio.TextManager.Interop> API입니다. 예를 들어 비 편집기 서비스 사이 이동 하려면 어댑터, Visual Studio 셸 명령 및 편집기 서비스를 사용할 수 있습니다. \(이 어떻게 편집기는 현재 Visual Studio에서 호스트 합니다.\) 어댑터는 또한 Visual Studio에서 제대로 작동 하려면 레거시 편집기 및 언어 서비스 확장을 사용 합니다.  
  
## 편집기 어댑터를 사용 하 여  
 <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService> 새 편집기 인터페이스 및 레거시 인터페이스 사이 전환 하는 메서드 및 어댑터를 만드는 메서드를 제공 합니다.  
  
 이 서비스는 MEF 구성 요소 파트를 사용 하는 경우 다음과 같이 서비스를 가져올 수 있습니다.  
  
```  
[Import(typeof(IVsEditorAdaptersFactoryService))]  
internal IVsEditorAdaptersFactoryService editorFactory;  
```  
  
 비 MEF 구성 요소에서이 서비스를 사용 하려는 경우이 항목의 뒷부분에 나오는 "를 사용 하 여 Visual Studio 편집기 서비스에는 비 MEF 구성 요소" 섹션의 지침을 따릅니다.  
  
## 새 편집기 API 및 레거시 API 간 전환  
 다음 메서드를 사용 하 여 편집기 개체와 기존 인터페이스 간에 전환할 수 있습니다.  
  
|메서드|변환|  
|---------|--------|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetBufferAdapter%2A>|변환 된 <xref:Microsoft.VisualStudio.Text.ITextBuffer> 에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>합니다.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetDataBuffer%2A>|변환 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 에 <xref:Microsoft.VisualStudio.Text.ITextBuffer>합니다.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetDocumentBuffer%2A>|변환 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 에 <xref:Microsoft.VisualStudio.Text.ITextBuffer>합니다.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetViewAdapter%2A>|변환 된 <xref:Microsoft.VisualStudio.Text.Editor.ITextView> 에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>합니다.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetWpfTextView%2A>|변환 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 에 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView>합니다.|  
  
## 어댑터 만들기  
 레거시 인터페이스에 대 한 어댑터를 만들려면 다음 메서드를 사용 합니다.  
  
|메서드|변환|  
|---------|--------|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsCodeWindowAdapter%2A>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>를 만듭니다.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextBufferAdapter%2A>|만듭니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 는 지정 된 <xref:Microsoft.VisualStudio.Utilities.IContentType>합니다.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextBufferAdapter%2A>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>를 만듭니다.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextBufferCoordinatorAdapter%2A>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator>를 만듭니다.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextViewAdapter%2A>|만듭니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 에 대 한는 <xref:Microsoft.VisualStudio.Text.Editor.ITextViewRoleSet>합니다.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextViewAdapter%2A>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>를 만듭니다.|  
  
## 비관리 코드에서 어댑터 만들기  
 모든 어댑터 클래스에 로컬로 등록 된 공동 creatable를 사용 하 여 인스턴스화할 수는 `VsLocalCreateInstance()` 함수입니다.  
  
 모든 어댑터의 vsshlids.h 파일에 정의 된 Guid를 사용 하 여 만들어지는... Visual Studio SDK 설치의 \\VisualStudioIntegration\\Common\\Inc\\ 폴더입니다. VsTextBufferAdapter의 인스턴스를 만들려면 다음 코드를 사용 합니다.  
  
```  
IVsTextBuffer *pBuf = NULL;  
VsLocalCreateInstance(CLSID_VsTextBuffer, NULL, CLSCTX_INPROC_SERVER, IID_IVsTextBuffer, (void**)&pBuf);  
```  
  
## 관리 코드에서 어댑터 만들기  
 관리 코드에서 비관리 코드에 대해 설명 된 것과 동일한 방식으로 공동 어댑터를 만들 수 있습니다. 만들고 어댑터와 상호 작용할 수 있는 MEF 서비스를 사용할 수 있습니다. 어댑터는 이러한 방식으로 공동으로 만들 때 사용할 수 있는 것 보다 더 세분화 된 제어를 수 있습니다.  
  
#### IVsTextView에 대 한 어댑터를 만들려면  
  
1.  Microsoft.VisualStudio.Editor.dll에 대 한 참조를 추가 합니다. 다음 사항을 확인 `CopyLocal` 로 설정 된 `false`합니다.  
  
2.  인스턴스화하는 <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService>, 다음과 같이 합니다.  
  
    ```  
    using Microsoft.VisualStudio.Editor;  
    ...  
    IVsEditorAdaptersFactoryService adapterFactoryService = ComponentModel.GetService<IVsEditorAdaptersFactoryService>();  
    ```  
  
3.  `CreateX()` 메서드를 호출합니다.  
  
    ```  
    adapterFactoryService.CreateTextViewAdapter(textView);  
    ```  
  
## 관리 되지 않는 코드에서 직접 Visual Studio 편집기를 사용 하 여  
 Microsoft.VisualStudio.Platform.VSEditor 네임 스페이스와 Microsoft.VisualStudio.Platform.VSEditor.Interop 네임 스페이스 IVx 인터페이스를 COM 호출 가능 인터페이스를 노출합니다. 예를 들어 Microsoft.VisualStudio.Platform.VSEditor.Interop.IVxTextBuffer 인터페이스는 COM의 버전이 <xref:Microsoft.VisualStudio.Text.ITextBuffer> 인터페이스입니다.`IVxTextBuffer`, 버퍼 스냅숏에 대 한 액세스를 얻을, 버퍼를 수정를 사용 하 여 버퍼에서 텍스트 변경 이벤트를 수신 및 추적 지점 및 범위를 만들 수 있습니다. 다음 단계에 액세스 하는 방법을 보여 줍니다는 `IVxTextBuffer` 에서 `IVsTextBuffer`합니다.  
  
#### IVxTextBuffer 가져오려는  
  
1.  IVx \* 인터페이스에 대 한 정의에 VSEditor.h 파일에는... Visual Studio SDK 설치의 \\VisualStudioIntegration\\Common\\Inc\\ 폴더입니다.  
  
2.  다음 코드를 사용 하 여 텍스트 버퍼를 인스턴스화하는 `IVsUserData->GetData()` 메서드. 다음 코드에서 `pData` 에 대 한 포인터는 `IVsUserData` 개체입니다.  
  
    ```  
    #include <textmgr.h>  
    #include <VSEditor.h>  
    #include <vsshlids.h>  
  
    CComPtr<IVsTextBuffer> pVsTextBuffer;  
    CComPtr<IVsUserData> pData;  
    CComPtr<IVxTextBuffer> pVxBuffer;  
    ...  
    if (SUCCEEDED(pVsTextBuffer->QueryInterface(IID_IVsUserData, &pData))  
    {  
        CComVariant vt;  
        if (SUCCEEDED(pData->GetData(GUID_VxTextBuffer, &vt)) &&  
        (vt.Type == VT_UNKNOWN) && (vt.punkVal != NULL))  
        {  
            vt.punkVal->QueryInterface(IID_IVxTextBuffer, (void**)&pVxBuffer);  
        }  
    }  
    ```  
  
## Visual Studio 편집기 서비스를 사용 하 여 비 MEF 구성 요소에서  
 MEF를 사용 하지 않는 관리 되는 코드 구성 요소가 있는 경우 Visual Studio 편집기의 서비스를 사용 하려면 ComponentModelHost VSPackage를 포함 하는 어셈블리에 대 한 참조를 추가 하 고 해당 SComponentModel 서비스 가져오기 해야 합니다.  
  
#### Visual Studio 편집기 구성 요소에서 비 MEF 구성 요소를 사용 하려면  
  
1.  Microsoft.VisualStudio.ComponentModelHost.dll 어셈블리에 대 한 참조 추가... Visual Studio 설치의 \\Common7\\IDE\\ 폴더입니다. 다음 사항을 확인 `CopyLocal` 로 설정 된 `false`합니다.  
  
2.  추가 전용 `IComponentModel` 다음과 같이 Visual Studio 편집기 서비스를 사용 하 여 원하는 클래스에는 멤버입니다.  
  
    ```  
    using Microsoft.VisualStudio.ComponentModelHost;  
    ....  
    private IComponentModel componentModel;  
    ```  
  
3.  구성 요소에 대 한 초기화 메서드에서 구성 요소 모델을 인스턴스화하십시오.  
  
    ```  
    componentModel =  
     (IComponentModel)Package.GetGlobalService(typeof(SComponentModel));  
    ```  
  
4.  그런 다음 Visual Studio 편집기 서비스 중 하나를 호출 하 여 가져올 수 있습니다는 `IComponentModel.GetService<T>()` 원하는 서비스에 대 한 메서드.  
  
    ```  
    textBufferFactoryService =  
         componentModel.GetService<ITextBufferFactoryService>();     
    ```