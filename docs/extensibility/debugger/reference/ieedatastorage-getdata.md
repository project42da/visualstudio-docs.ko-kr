---
title: "IEEDataStorage::GetData | Microsoft Docs"
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
  - "IEEDataStorage::GetData"
helpviewer_keywords: 
  - "IEEDataStorage::GetData"
ms.assetid: 4d384039-73d4-40b4-ace6-a2474c546397
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# IEEDataStorage::GetData
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

개체에서 지정된 된 바이트 수를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetData(  
   ULONG  dataSize,  
   ULONG* sizeGotten,  
   BYTE*  data  
);  
```  
  
```c#  
int GetData(  
   uint     dataSize,  
   out uint sizeGotten,  
   byte[]   data  
);  
```  
  
#### 매개 변수  
 `dataSize`  
 \[in\] 검색할 바이트 수 \(의 `data` 배열 해야이 바이트 수가 적어도 보유\).  
  
 `sizeGotten`  
 \[out\] 실제로 검색 된 바이트 수를 반환 합니다.  
  
 `data`  
 \[in, out\] 요청 된 데이터를 사용 하 여 채워질 배열입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드의 권장 되는 사용 바이트 단위로 검색 프로세스를 건너뛸 수 있는 방법이 없기 때문을 로컬 배열에 모든 데이터 바이트를 검색 하는 것입니다.  이 경우에 매개 변수 `dataSize` 에서 값을 반환 합니다는 [GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md) 메서드.  
  
## 참고 항목  
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md)