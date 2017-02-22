---
title: "IDebugDocumentTextEvents2::onRemoveText | Microsoft Docs"
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
  - "IDebugDocumentTextEvents2::OnRemoveText"
helpviewer_keywords: 
  - "IDebugDocumentTextEvents2::onRemoveText"
ms.assetid: 1ebeabb2-52a1-4ccc-83cd-9ae7c3541783
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDocumentTextEvents2::onRemoveText
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 패키지 텍스트를 문서에서 제거 되었음을 알립니다.  
  
## 구문  
  
```cpp#  
HRESULT onRemoveText(   
   TEXT_POSITION pos,  
   DWORD         dwNumToRemove  
);  
```  
  
```c#  
int onRemoveText(   
   enum_TEXT_POSITION pos,  
   uint               dwNumToRemove  
);  
```  
  
#### 매개 변수  
 `pos`  
 \[in\] A [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md) 구조를 나타내는 텍스트를 제거 했습니다.  
  
 `dwNumToRemove`  
 \[in\] 제거 된 텍스트의 문자 수를 지정 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)   
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md)