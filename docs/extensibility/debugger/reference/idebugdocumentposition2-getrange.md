---
title: "IDebugDocumentPosition2::GetRange | Microsoft Docs"
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
  - "IDebugDocumentPosition2::GetRange"
helpviewer_keywords: 
  - "IDebugDocumentPosition2::GetRange"
ms.assetid: 91a06ee7-253a-4215-be22-04bf57305aa8
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDocumentPosition2::GetRange
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

범위를 대 한이 문서의 위치를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetRange(   
   TEXT_POSITION* pBegPosition,  
   TEXT_POSITION* pEndPosition  
);  
```  
  
```c#  
int GetRange(   
   TEXT_POSITION[] pBegPosition,  
   TEXT_POSITION[] pEndPosition  
);  
```  
  
#### 매개 변수  
 `pBegPosition`  
 \[in, out\] A [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md) 구조는 시작 위치를 사용 하 여 채워집니다.  이 정보가 필요 하지 않으면이 인수는 null 값으로 설정 합니다.  
  
 `pEndPosition`  
 \[in, out\] A [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md) 사용 하 여 끝 위치를 입력 하는 구조입니다.  이 정보가 필요 하지 않으면이 인수는 null 값으로 설정 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 문서 위치 위치 중단점에 대해 지정 된 범위에 미리 실제로 코드에 기여에 대 한 문을 검색 합니다 \(DE\)는 디버그 엔진에서 사용 됩니다.  예를 들어, 다음 코드를 고려하십시오.  
  
```  
Line 5: // comment  
Line 6: x = 1;  
```  
  
 5 줄 코드가 디버깅 되 고 있는 프로그램에 기여 합니다.  앞으로 일정 시간 코드에 기여 하는 첫 번째 줄을 검색 하는 DE 디버거 5 줄에 중단점을 설정 하고자 할 경우 디버거에 추가 후보 줄 중단점 제대로 배치 될 수 있는 범위를 지정 합니다.  중단점을 받을 수 있는 줄을 찾을 때까지 있는 DE 다음 앞으로 해당 줄을 통해 검색 합니다.  
  
## 참고 항목  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)   
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md)