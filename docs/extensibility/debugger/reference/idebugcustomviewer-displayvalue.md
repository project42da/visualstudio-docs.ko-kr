---
title: "IDebugCustomViewer::DisplayValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugCustomViewer::DisplayValue"
helpviewer_keywords: 
  - "IDebugCustomViewer::DisplayValue"
ms.assetid: 7a538248-5ced-450e-97cd-13fabe35fb1c
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugCustomViewer::DisplayValue
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 지정 된 값을 표시 합니다 호출 됩니다.  
  
## 구문  
  
```cpp#  
HRESULT DisplayValue(  
   HWND             hwnd,  
   DWORD            dwID,  
   IUnknown *       pHostServices,  
   IDebugProperty3* pDebugProperty);  
);  
```  
  
```c#  
int DisplayValue(  
   IntPtr          hwnd,   
   uint            dwID,   
   object          pHostServices,   
   IDebugProperty3 pDebugProperty  
);  
```  
  
#### 매개 변수  
 `hwnd`  
 \[in\] 부모 창  
  
 `dwID`  
 \[in\] 두 개 이상의 형식을 지 원하는 뷰어 사용자 지정에 대 한 ID입니다.  
  
 `pHostServices`  
 \[in\] 예약되었습니다.  항상 설정 합니다 null입니다.  
  
 `pDebugProperty`  
 \[in\] 표시 하는 값을 검색 하는 데 사용할 수 있는 인터페이스입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  
  
## 설명  
 이 메서드 됩니다 필요한 창 작성, 값 표시, 입력, 기다린 후 호출자에 게 반환 하기 전에 모든 창을 닫습니다 표시 "모달"입니다.  따라서 메서드 만들기 창 소멸에 사용자 입력을 기다리는 중에 \[출력\] 창에서 속성 값을 표시 하는 모든 측면을 처리 해야 합니다.  
  
 지원에서 값을 변경 하는 주어진 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 개체를 사용할 수 있습니다의 [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md) 메서드\-값 문자열로 표현 될 수 있으면 합니다.  그렇지 않으면 사용자 지정 인터페이스를 만드는 데 필요한 됩니다\-이 구현 식 계산기에 단독으로 `DisplayValue` 메서드\-구현 하는 동일한 개체에는 `IDebugProperty3` 인터페이스입니다.  이 사용자 지정 인터페이스는 복잡성 또는 임의 크기의 데이터를 변경 하는 방법을 제공 됩니다.  
  
## 참고 항목  
 [IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)