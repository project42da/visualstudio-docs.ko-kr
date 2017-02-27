---
title: "IDebugDocumentPositionOffset2::GetRange | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugDocumentPositionOffset2::GetRange"
ms.assetid: 27da7130-0932-4f97-abde-05e6fb018606
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# IDebugDocumentPositionOffset2::GetRange
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

범위는 현재 문서의 위치를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetRange(  
   DWORD* pdwBegOffset,  
   DWORD* pdwEndOffset  
);  
```  
  
```c#  
public int GetRange(  
   ref uint pdwBegOffset,  
   ref uint pdwEndOffset  
);  
```  
  
#### 매개 변수  
 `pdwBegOffset`  
 \[in, out\] 범위의 시작 위치에 대 한 오프셋입니다.  이 정보가 필요 하지 않으면이 매개 변수를 null 값으로 설정 합니다.  
  
 `pdwEndOffset`  
 \[in, out\] 범위의 끝 위치에 대 한 오프셋입니다.  이 정보가 필요 하지 않으면이 매개 변수를 null 값으로 설정 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 문서 위치 위치 중단점에 대해 지정 된 범위에 미리 실제로 코드에 기여에 대 한 문을 검색 합니다 \(DE\)는 디버그 엔진에서 사용 됩니다.  예를 들어, 다음 코드를 고려하십시오.  
  
```  
Line 5: // comment  
Line 6: x = 1;  
```  
  
 5 줄 코드가 디버깅 되 고 있는 프로그램에 기여 합니다.  앞으로 일정 시간 코드에 기여 하는 첫 번째 줄을 검색 하는 DE 디버거 5 줄에 중단점을 설정 하고자 할 경우 디버거에 추가 후보 줄 중단점 정확 하 게 배치 될 수 있는 범위를 지정 합니다.  중단점을 받을 수 있는 줄을 찾을 때까지 있는 DE 다음 앞으로 해당 줄을 통해 검색 합니다.  
  
## 참고 항목  
 [IDebugDocumentPositionOffset2](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2.md)   
 [GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)