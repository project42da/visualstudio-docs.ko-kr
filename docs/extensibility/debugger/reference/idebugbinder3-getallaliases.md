---
title: "IDebugBinder3::GetAllAliases | Microsoft Docs"
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
  - "IDebugBinder3::GetAllAliases"
helpviewer_keywords: 
  - "IDebugBinder3::GetAllAliases 메서드"
ms.assetid: 1f9ab2ee-2ab3-4a61-8b99-95dd7fdf3511
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugBinder3::GetAllAliases
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드의 별칭의 목록이 프로그램을 검색합니다.  
  
## 구문  
  
```cpp  
HRESULT GetAllAliases(  
   UINT          uRequest,  
   IDebugAlias** ppAliases,  
   UINT*         puFetched  
);  
```  
  
```c#  
int GetAllAliases(  
   uint          uRequest,   
   IDebugAlias[] ppAliases,   
   out uint      puFetched  
);  
```  
  
#### 매개 변수  
 `uRequest`  
 \[in\] 최대 수의 별칭을 반환 합니다 \(전달 되는 배열의 길이 지정 합니다. `ppAliases`\).  
  
 `ppAliases`  
 \[in, out\] 배열을 사용 하 여 별칭을 채우기 위해 \(null 값인 경우 및 `uRequest` 0, 반환 될 수 있는 별칭 수가 반환 됩니다 `puFetched`\).  
  
 `puFetched`  
 \[out\] 가져온 별칭의 수를 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)