---
title: "IDebugStackFrame2::GetPhysicalStackRange | Microsoft Docs"
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
  - "IDebugStackFrame2::GetPhysicalStackRange"
helpviewer_keywords: 
  - "IDebugStackFrame2::GetPhysicalStackRange"
ms.assetid: 2f6992e2-ac1c-433f-83b7-a7f83a4ce63d
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugStackFrame2::GetPhysicalStackRange
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

스택 프레임과 연결 된 실제 주소는 컴퓨터에 종속 표현을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetPhysicalStackRange (   
   UINT64* paddrMin,  
   UINT64* paddrMax  
);  
```  
  
```c#  
int GetPhysicalStackRange (   
   out ulong paddrMin,  
   out ulong paddrMax  
);  
```  
  
#### 매개 변수  
 `paddrMin`  
 \[out\] 이 스택 프레임과 연결 된 낮은 실제 주소를 반환 합니다.  
  
 `paddrMax`  
 \[out\] 이 스택 프레임과 연결 된 가장 높은 실제 주소를 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드에 의해 반환 되는 정보 세션 디버그 매니저 \(SDM\)을 사용 하 여 스택 프레임을 정렬 합니다.  
  
 호출 스택 아래로, 즉, 점점 낮은 메모리 주소에 추가 되어 새 스택 프레임 증가 것으로 간주 됩니다.  런타임 아키텍처가이 가정에 맞는 실제 스택 범위를 제공 해야 합니다.  
  
## 참고 항목  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)