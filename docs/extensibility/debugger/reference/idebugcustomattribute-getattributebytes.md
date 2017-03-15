---
title: "IDebugCustomAttribute::GetAttributeBytes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugCustomAttribute::GetAttributeBytes"
helpviewer_keywords: 
  - "IDebugCustomAttribute::GetAttributeBytes"
ms.assetid: cf34583b-6530-4dcc-89f8-eb27e4e8d594
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugCustomAttribute::GetAttributeBytes
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

특성 정보를 blob 바이트 수를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetAttributeBytes(   
   BYTE*  ppBlob,  
   DWORD* pdwLen  
);  
```  
  
```c#  
int GetAttributeBytes(  
   ref byte[] ppBlob,   
   ref uint   pdwLen  
);  
```  
  
#### 매개 변수  
 `ppBlob`  
 \[in, out\] 특성 바이트를 사용 하 여 채워지는 배열입니다.  
  
 `pdwLen`  
 \[in, out\] 최대 바이트 수를 반환 하려면 지정은 `ppBlob` 배열 및 배열에 실제로 쓴 바이트 수를 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 설정에서 `ppBlob` 바이트 사용 가능한 특성을 매개 변수에 null 값의 개수를 반환 합니다.  다음 배열 할당 하 고 해당 배열에 대 한 전달의 `ppBlob` 매개 변수.  
  
 원시 데이터를의 사용자 지정 특성 특성 바이트를 나타냅니다.  
  
## 참고 항목  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)