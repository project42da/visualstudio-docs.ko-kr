---
title: "IDebugDocumentTextEvents2::onInsertText | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDocumentTextEvents2::OnInsertText"
helpviewer_keywords: 
  - "IDebugDocumentTextEvents2::onInsertText"
ms.assetid: 6040181f-7288-4a42-953c-d23f74200431
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugDocumentTextEvents2::onInsertText
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

텍스트를 문서에 삽입 한 디버그 패키지를 알립니다.  
  
## 구문  
  
```cpp#  
HRESULT onInsert(   
   TEXT_POSITION pos,  
   DWORD         dwNumToInsert  
);  
```  
  
```c#  
int onInsert(   
   enum_TEXT_POSITION pos,  
   uint               dwNumToInsert  
);  
```  
  
#### 매개 변수  
 `pos`  
 \[in\] A [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md) 텍스트 삽입 된 위치를 나타내는 구조입니다.  
  
 `dwNumToInsert`  
 \[in\] 삽입 된 텍스트의 문자 수를 지정 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)   
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md)