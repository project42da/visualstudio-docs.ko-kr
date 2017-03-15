---
title: "IDebugPortPicker::DisplayPortPicker | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DisplayPortPicker"
  - "IDebugPortPicker::DisplayPortPicker"
ms.assetid: 08511ef5-be64-4069-b169-a569cc94bc64
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugPortPicker::DisplayPortPicker
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

포트를 선택할 수 있도록 하는 지정 된 대화 상자를 표시 합니다.  
  
## 구문  
  
```cpp#  
HRESULT DisplayPortPicker(  
   HWND hwndParentDialog,  
   BSTR* pbstrPortId  
);  
```  
  
```c#  
public int DisplayPortPicker(  
   int hwndParentDialog,  
   out string pbstrPortId  
);  
```  
  
#### 매개 변수  
 `hwndParentDialog`  
 \[in\] 부모 대화 상자에 대 한 핸들입니다.  
  
 `pbstrPortId`  
 \[out\] 포트 식별자 문자열입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 값이 `S_FALSE` \(또는 반환 값이 `S_OK` 와 `BSTR` 설정 `NULL`\) 사용자를 눌렀음을 나타내는  **취소**.  
  
## 참고 항목  
 [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)