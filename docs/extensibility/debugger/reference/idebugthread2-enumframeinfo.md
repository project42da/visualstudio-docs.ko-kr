---
title: "IDebugThread2::EnumFrameInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugThread2::EnumFrameInfo"
helpviewer_keywords: 
  - "IDebugThread2::EnumFrameInfo"
ms.assetid: 17914a71-10ea-4b6f-8982-e364f87dca53
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugThread2::EnumFrameInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 스레드에 대 한 스택 프레임의 목록을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumFrameInfo (   
   FRAMEINFO_FLAGS        dwFieldSpec,  
   UINT                   nRadix,  
   IEnumDebugFrameInfo2** ppEnum  
);  
```  
  
```c#  
int EnumFrameInfo (   
   enum_FRAMEINFO_FLAGS     dwFieldSpec,  
   uint                     nRadix,  
   out IEnumDebugFrameInfo2 ppEnum  
);  
```  
  
#### 매개 변수  
 `dwFieldSpec`  
 \[in\] 플래그의 조합을 [FRAMEINFO\_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) 필드를 지정 하는 열거형의 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 구조는 데이터를 입력할 수 있습니다.  지정은 `FIF_FUNCNAME_FORMAT` 함수 이름을 단일 문자열로 형식을 지정 하는 플래그입니다.  
  
 `nRadix`  
 \[in\] 열거자의 숫자 정보를 서식 지정에 사용 되는 기 수입니다.  
  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) 목록을 포함 하는 개체 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 는 스택 프레임을 설명 하는 구조입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 스레드 프레임에서 처음 열거 된 현재 프레임을 사용 하 고 마지막으로 열거 된 가장 오래 된 프레임 열거 됩니다.  
  
## 참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [FRAMEINFO\_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)   
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)