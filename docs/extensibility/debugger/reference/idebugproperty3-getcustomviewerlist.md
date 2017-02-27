---
title: "IDebugProperty3::GetCustomViewerList | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProperty3::GetCustomViewerList"
helpviewer_keywords: 
  - "IDebugProperty3::GetCustomViewerList"
ms.assetid: 74490fd8-6f44-4618-beea-dab64961bb8a
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugProperty3::GetCustomViewerList
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 속성에 연결 된 사용자 지정 뷰어 목록을 가져옵니다.  
  
## 구문  
  
```cpp  
HRESULT GetCustomViewerList(  
   ULONG                celtSkip,  
   ULONG                celtRequested,  
   DEBUG_CUSTOM_VIEWER* rgViewers,  
   ULONG*               pceltFetched  
);  
```  
  
```c#  
int GetCustomViewerList(  
   uint                  celtSkip,  
   uint                  celtRequested,  
   DEBUG_CUSTOM_VIEWER[] rgViewers,  
   out uint              pceltFetched  
);  
```  
  
#### 매개 변수  
 `celtSkip`  
 \[in\] 검토자 수를 건너뛸 수 있습니다.  
  
 `celtRequested`  
 \[in\] 뷰어를 검색할 수 \(도 지정은 `rgViewers` 배열\).  
  
 `rgViewers`  
 \[in, out\] 배열 [DEBUG\_CUSTOM\_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md) 구조체를 채워야 합니다.  
  
 `pceltFetched`  
 \[out\] 반환 되는 실제 보는 사람 수 있습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 형식을 시각화 도우미를 지원 하기 위해이 메서드를 호출 전달의 [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md) 메서드.  식 계산기도이 속성 형식에 사용자 지정 뷰어를 지원 하는 경우이 메서드는 적절 한 사용자 지정 뷰어 목록에 추가할 수 있습니다.  
  
 참조 하십시오 [시각화 도우미 형식 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md) 형식 시각화 및 사용자 지정 뷰어 간의 차이점에 대 한 자세한 내용은.  
  
## 예제  
 다음 예제에서는이 메서드를 구현 하는 방법을 보여 줍니다 있는  **CProperty** 를 노출 하는 개체는 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 인터페이스.  
  
```cpp#  
STDMETHODIMP CProperty::GetCustomViewerList(ULONG celtSkip, ULONG celtRequested, DEBUG_CUSTOM_VIEWER* prgViewers, ULONG* pceltFetched)  
{  
    if (NULL == prgViewers)  
    {  
        return E_POINTER;  
    }  
  
    if (GetVisualizerService())  
    {  
        return m_pIEEVisualizerService->GetCustomViewerList(celtSkip, celtRequested, prgViewers, pceltFetched);  
    }  
    else  
    {  
        return E_NOTIMPL;  
    }  
}  
```  
  
## 참고 항목  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [DEBUG\_CUSTOM\_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md)   
 [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)   
 [시각화 도우미 형식 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)