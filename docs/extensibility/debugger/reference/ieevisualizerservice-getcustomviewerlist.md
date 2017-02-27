---
title: "IEEVisualizerService::GetCustomViewerList | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEEVisualizerService::GetCustomViewerList"
helpviewer_keywords: 
  - "IEEVisualizerService::GetCustomViewerList 메서드"
ms.assetid: 249d26ca-914f-43af-a400-8162477223f4
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IEEVisualizerService::GetCustomViewerList
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는이 서비스에서 인식 하는 형식 시각화 도우미 목록을 반환 합니다.  
  
## 구문  
  
```cpp  
HRESULT GetCustomViewerList(  
   ULONG                celtSkip,  
   ULONG                celtRequested,  
   DEBUG_CUSTOM_VIEWER* rgViewers,  
   ULONG*               pceltFetched  
);  
```  
  
```c#  
int GetCustomViewerList(  
   uint                  celtSkip,  
   uint                  celtRequested,  
   DEBUG_CUSTOM_VIEWER[] rgViewers,  
   out uint              pceltFetched  
);  
```  
  
#### 매개 변수  
 `celtSkip`  
 \[in\] 수 건너뛸 수 시각화 도우미입니다.  
  
 `celRequested`  
 \[in\] 검색할 수 있는 시각화 도우미의 수 \(도 지정는 `rgViewers` 배열\).  
  
 `rgViewers`  
 \[in, out\] 배열 [DEBUG\_CUSTOM\_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md) 구조체를 채워야 합니다.  
  
 `pceltFetched`  
 \[out\] 시각화 도우미의 수를 실제로 검색 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)형식을 시각화 도우미에 대 한 요청이 지원의 일환으로이 메서드에 전달합니다.  식 계산기는 동일한 형식에 대해 사용자 지정 뷰어를 제공 하는 경우 작성 한 적절 하 게 추가할 수 있습니다 [DEBUG\_CUSTOM\_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md) 이 사용자 지정 뷰어를 목록에 대 한 구조입니다.  [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) 이 추가로 뷰어를 반영 합니다.  
  
 참조 하십시오 [시각화 도우미 형식 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md) 시각화 하 고 보는 사람 간의 차이점에 대 한 자세한 내용은.  
  
## 참고 항목  
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [DEBUG\_CUSTOM\_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md)   
 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)   
 [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md)   
 [시각화 도우미 형식 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)