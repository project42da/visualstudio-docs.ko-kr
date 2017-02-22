---
title: "IDebugDocumentTextEvents2::onUpdateTextAttributes | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDocumentTextEvents2::OnUpdateTextAttributes"
helpviewer_keywords: 
  - "IDebugDocumentTextEvents2::onUpdateTextAttributes"
ms.assetid: eb68d69a-1ad9-4ce4-84e1-40979ef16634
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDocumentTextEvents2::onUpdateTextAttributes
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

문서에서 텍스트 특성 업데이트 된 디버그 패키지를 알립니다.  
  
## 구문  
  
```cpp#  
HRESULT onUpdateTextAttributes(   
   TEXT_POSITION pos,  
   DWORD         dwNumToUpdate  
);  
```  
  
```c#  
int onUpdateTextAttributes(   
   enum_TEXT_POSITION pos,  
   uint               dwNumToUpdate  
);  
```  
  
#### 매개 변수  
 `pos`  
 \[in\] A [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md) 텍스트 특성 업데이트 된 위치를 나타내는 구조입니다.  
  
 `dwNumToUpdate`  
 \[in\] 업데이트 된 텍스트의 문자 수를 지정 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)   
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md)