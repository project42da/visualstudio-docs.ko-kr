---
title: IDebugCustomViewer | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCustomViewer
helpviewer_keywords:
- IDebugCustomViewer interface
ms.assetid: 7aca27d3-c7b8-470f-b42c-d1e9d9115edd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3fb70365304883abe99a87cfec5e78bbed89f2dd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugcustomviewer"></a>IDebugCustomViewer
이 인터페이스를 사용 하는 식 계산기 (EE)에 어떤 형식이 필요한 속성의 값을 표시 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugCustomViewer : IUknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 EE를 사용자 지정 형식에서 속성의 값을 표시 하려면이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 COM의에 대 한 호출 `CoCreateInstance` 함수는이 인터페이스를 인스턴스화합니다. `CLSID` 에 전달 된 `CoCreateInstance` 레지스트리에서 가져옵니다. 에 대 한 호출 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) 레지스트리의 위치를 가져옵니다. 이 예제에서는 뿐만 아니라 세부 정보에 대 한 설명을 참조 하세요.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 이 인터페이스는 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[DisplayValue](../../../extensibility/debugger/reference/idebugcustomviewer-displayvalue.md)|지정된 된 값을 표시 하는 데 필요한 수행 하지 않습니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 일반적인 방법으로 속성의 값을 표시할 수 없는 경우 사용-등 데이터 테이블 또는 다른 복합 속성을 사용 합니다. 표시 되는 사용자 지정 뷰어와 `IDebugCustomViewer` 인터페이스를 EE에 관계 없이 특정 형식의 데이터를 표시 하기 위한 외부 프로그램은 형식 시각화 도우미와 다릅니다. EE 해당 EE에만 적용 되는 사용자 지정 뷰어를 구현 합니다. 사용자가 어떤 유형의 시각화 도우미 형식 시각화 도우미 또는 사용자 지정 뷰어를 사용 하려면 선택 합니다. 참조 [Visualizing 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md) 이 프로세스에 대 한 자세한 내용은 합니다.  
  
 사용자 지정 뷰어는 동일한 방식으로는 EE에 등록 되 고 따라서 언어 GUID와 공급 업체 GUID 필요 합니다. 정확한 메트릭을 (또는 레지스트리 항목 이름)는 EE에만 알려집니다. 이 메트릭은에 반환 되는 [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md) 구조에 대 한 호출에서 반환 되는 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)합니다. 에 대 한 메트릭을에 저장 된 값의 `CLSID` COM의에 전달 되는 `CoCreateInstance` (예제 참조) 함수입니다.  
  
 [디버깅할 수 있도록 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) 함수 `SetEEMetric`, 사용자 지정 뷰어를 등록에 사용할 수 있습니다. "식 계산기" 레지스트리 섹션을 참조 `Debugging SDK Helpers` 는 특정 레지스트리 키에 대 한 사용자 지정 뷰어 필요 합니다. 사용자 지정 뷰어는 식 계산기에서는 여러 가지 미리 정의 된 메트릭을 (implementer EE의 문자로 정의)이 표시 되는 메트릭을 하나만 필요 함을 note 합니다.  
  
 일반적으로 사용자 지정 뷰어를 제공 데이터의 읽기 전용 보기 이후에 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 인터페이스에 제공 된 [DisplayValue](../../../extensibility/debugger/reference/idebugcustomviewer-displayvalue.md) 에 속성의 값을 문자열로 제외 하 고 변경 하기 위한 메서드가 없습니다. 사용자 지정 인터페이스를 구현 하는 동일한 개체에 대 EE 임의의 데이터 블록의 변경 작업을 지원 하기 위해 구현는 `IDebugProperty3` 인터페이스입니다. 이 사용자 지정 인터페이스는 임의의 데이터 블록을 변경 하는 데 필요한 방법을 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="example"></a>예제  
 이 예제에 해당 속성에는 모든 사용자 지정 뷰어가 경우 속성에서 첫 번째 사용자 지정 뷰어를 가져오는 방법을 보여 줍니다.  
  
```cpp  
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
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)   
 [디버깅을 위한 도우미 SDK](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)