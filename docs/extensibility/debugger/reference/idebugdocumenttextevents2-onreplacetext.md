---
title: "IDebugDocumentTextEvents2::onReplaceText | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDocumentTextEvents2::OnReplaceText"
helpviewer_keywords: 
  - "IDebugDocumentTextEvents2::onReplaceText"
ms.assetid: cb39f025-66d8-4dc0-bef6-1bdc8e07db92
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugDocumentTextEvents2::onReplaceText
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

텍스트 문서에서 대체 되었습니다 디버그 패키지를 알립니다.  
  
## 구문  
  
```cpp#  
HRESULT onReplaceText(   
   TEXT_POSITION pos,  
   DWORD         dwNumToReplace  
);  
```  
  
```c#  
int onReplaceText(   
   enum_TEXT_POSITION pos,  
   uint               dwNumToReplace  
);  
```  
  
#### 매개 변수  
 `pos`  
 \[in\] A [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md) 를 나타내는 텍스트를 바꿨습니다.  
  
 `dwNumToReplace`  
 \[in\] 대체 된 텍스트의 문자 수를 지정 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)   
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md)