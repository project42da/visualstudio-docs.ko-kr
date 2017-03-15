---
title: "IDebugProperty3::GetCustomViewerCount | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProperty3::GetCustomViewerCount"
helpviewer_keywords: 
  - "IDebugProperty3::GetCustomViewerCount"
ms.assetid: dc5bb3e4-dc85-46e4-98fa-c6be8583b985
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugProperty3::GetCustomViewerCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 속성에 사용할 수 있는 사용자 지정 사용자의 수를 가져옵니다.  
  
## 구문  
  
```cpp  
HRESULT GetCustomViewerCount(  
   ULONG* pcelt  
);  
```  
  
```c#  
int GetCustomViewerCount(  
   out uint pcelt  
);  
```  
  
#### 매개 변수  
 `pcelt`  
 \[out\] 이 속성에 사용할 수 있는 사용자 지정 사용자의 수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 형식을 시각화 도우미를 지원 하기 위해이 메서드를 호출 전달의 [GetCustomViewerCount](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) 메서드.  이 속성의이 형식에 대해 식 계산기에서는 지원 되는 사용자 지정 뷰어에서이 메서드는 수 사용자 지정 뷰어를 반환 되는 값에 추가 됩니다.  
  
 형식 시각화 도우미 및 사용자 지정 뷰어는 차이점에 대 한 자세한 내용은 참조 하십시오 [시각화 도우미 형식 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md).  
  
## 예제  
 다음 예제에서는이 메서드를 구현 하는 방법을 보여 줍니다 있는  **CProperty** 를 노출 하는 개체는 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 인터페이스.  
  
```cpp#  
STDMETHODIMP CProperty::GetCustomViewerCount(ULONG* pcelt)  
{  
    if (pcelt == NULL)  
    {  
        return E_POINTER;  
    }  
  
    if (GetVisualizerService())  
    {  
        return m_pIEEVisualizerService->GetCustomViewerCount(pcelt);  
    }  
    else  
    {  
        return E_NOTIMPL;  
    }  
}  
```  
  
## 참고 항목  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [GetCustomViewerCount](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md)   
 [시각화 도우미 형식 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)