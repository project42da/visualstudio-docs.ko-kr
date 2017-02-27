---
title: "IDebugCustomViewer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugCustomViewer"
helpviewer_keywords: 
  - "IDebugCustomViewer 인터페이스"
ms.assetid: 7aca27d3-c7b8-470f-b42c-d1e9d9115edd
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# IDebugCustomViewer
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 식 계산기를 \(EE\) 서식 필요에 속성 값을 표시할 수 있습니다.  
  
## 구문  
  
```  
IDebugCustomViewer : IUknown  
```  
  
## 구현자 참고 사항  
 EE 속성의 값을 사용자 지정 형식으로 표시 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 COM의 호출 `CoCreateInstance` 함수는이 인터페이스를 인스턴스화합니다.  `CLSID` 전달 된 `CoCreateInstance` 레지스트리에서 가져옵니다.  호출을 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) 레지스트리에서 위치를 가져옵니다.  참고 예제 뿐만 아니라 정보를 참조 하십시오.  
  
## 메서드에서 Vtable 순서  
 이 인터페이스에 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|---------|--------|  
|[DisplayValue](../../../extensibility/debugger/reference/idebugcustomviewer-displayvalue.md)|무엇이 든 지 주어진된 값을 표시 하지 않습니다.|  
  
## 설명  
 일반적인 방법으로 속성 값을 표시할 수 없는 경우이 인터페이스를 사용\-예의 데이터 테이블 또는 다른 복잡 한 속성 형식입니다.  로 표현 하 여 사용자 지정 뷰어를 있는 `IDebugCustomViewer` 인터페이스를 EE에 관계 없이 특정 형식의 데이터를 표시 하는 외부 프로그램입니다 형식 시각화 도우미에서 다릅니다.  EE는 EE에 관련 된 사용자 지정 뷰어를 구현 합니다.  사용자 종류, 형식 시각화 도우미를 또는 사용자 지정 뷰어에서 수를 사용 하 여 시각화 도우미를 선택 합니다.  참조 하십시오 [시각화 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md) 이 프로세스에 대 한 자세한 내용은.  
  
 사용자 지정 뷰어 같은 방법으로는 EE에 등록 되며 따라서 언어 GUID 및 공급 GUID가 필요 합니다.  EE에만 정확한 메트릭 \(또는 레지스트리 항목 이름\) 이라고 합니다.  이 메트릭을 반환 되는 [DEBUG\_CUSTOM\_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md) 를 차례로 호출 하 여 반환 되는 구조를 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md).  미터법에 저장 된 값이 있는 `CLSID` COM에 전달 된 `CoCreateInstance` 작동 \(예 참조\).  
  
 [디버깅을 위한 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) 함수를 `SetEEMetric`를 사용 하 여 사용자 지정 뷰어를 등록할 수 있습니다.  "식 계산기" 레지스트리 섹션을 참조 하십시오. `Debugging SDK Helpers` 는 특정 레지스트리 키에 대 한 사용자 지정 뷰어를 해야 합니다.  여러 가지 미리 정의 된 메트릭을 계산 열에서 사용 되는 반면 사용자 지정 뷰어 \(는 EE의 구현 자가 정의 됩니다\) 한 메트릭을 해야 한다는 note입니다.  
  
 이후 데이터의 읽기 전용 보기 사용자 지정 뷰어를 일반적으로 제공는 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 인터페이스를 제공 합니다 [DisplayValue](../../../extensibility/debugger/reference/idebugcustomviewer-displayvalue.md) 를 제외 하 고 해당 속성의 값을 문자열로 바꾸는 메서드가 없습니다.  임의의 데이터 블록을 변경할 수 EE에서 사용자 지정 인터페이스를 구현 하는 동일한 개체에 구현에서 `IDebugProperty3` 인터페이스입니다.  그런 다음이 사용자 지정 인터페이스는 임의의 블록의 데이터를 변경 하는 데 필요한 방법을 제공 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 예제  
 사용자 지정 뷰어는 해당 속성에 있는 경우 첫 번째 사용자 지정 뷰어 속성을 가져오는 방법을 보여 주는이 예제입니다.  
  
```cpp#  
IDebugCustomViewer *GetFirstCustomViewer(IDebugProperty2 *pProperty)  
{  
    // This string is typically defined globally.  For this example, it  
    // is defined here.  
    static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0Exp";  
    IDebugCustomViewer *pViewer = NULL;  
    if (pProperty != NULL) {  
        CComQIPtr<IDebugProperty3> pProperty3(pProperty);  
        if (pProperty3 != NULL) {  
            HRESULT hr;  
            ULONG viewerCount = 0;  
            hr = pProperty3->GetCustomViewerCount(&viewerCount);  
            if (viewerCount > 0) {  
                ULONG viewersFetched = 0;  
                DEBUG_CUSTOM_VIEWER viewerInfo = { 0 };  
                hr = pProperty3->GetCustomViewerList(0,  
                                                     1,  
                                                     &viewerInfo,  
                                                     &viewersFetched);  
                if (viewersFetched == 1) {  
                    CLSID clsidViewer = { 0 };  
                    CComPtr<IDebugCustomViewer> spCustomViewer;  
                    // Get the viewer's CLSID from the registry.  
                    ::GetEEMetric(viewerInfo.guidLang,  
                                  viewerInfo.guidVendor,  
                                  viewerInfo.bstrMetric,  
                                  &clsidViewer,  
                                  strRegistrationRoot);  
                    if (!IsEqualGUID(clsidViewer,GUID_NULL)) {  
                        // Instantiate the custom viewer.  
                        spCustomViewer.CoCreateInstance(clsidViewer);  
                        if (spCustomViewer != NULL) {  
                            pViewer = spCustomViewer.Detach();  
                        }  
                    }  
                }  
            }  
        }  
    }  
    return(pViewer);  
}  
```  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)   
 [디버깅을 위한 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)