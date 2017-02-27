---
title: "IEEDataStorage::GetSize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEEDataStorage::GetSize"
helpviewer_keywords: 
  - "IEEDataStorage::GetSize"
ms.assetid: 33d232c4-1239-4abc-922b-e1bc5b908169
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IEEDataStorage::GetSize
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 개체에 포함 된 바이트 수를 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetSize(  
   ULONG* size  
);  
```  
  
```c#  
int GetSize(  
   out uint size  
);  
```  
  
#### 매개 변수  
 `size`  
 \[out\] 이 개체에 포함 된 바이트 수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 사용은 [GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md) 실제 데이터 바이트를 검색 하는 방법입니다.  
  
## 참고 항목  
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)