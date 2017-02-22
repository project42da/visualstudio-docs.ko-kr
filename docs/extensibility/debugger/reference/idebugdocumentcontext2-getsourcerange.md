---
title: "IDebugDocumentContext2::GetSourceRange | Microsoft Docs"
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
  - "IDebugDocumentContext2::GetSourceRange"
helpviewer_keywords: 
  - "IDebugDocumentContext2::GetSourceRange"
ms.assetid: 5903c75e-5390-4d13-9314-1ee276255313
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDocumentContext2::GetSourceRange
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

문서에는 소스 코드 범위를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetSourceRange(   
   TEXT_POSITION* pBegPosition,  
   TEXT_POSITION* pEndPosition  
);  
```  
  
```c#  
int GetSourceRange(   
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
 원본 범위의 현재 방금 코드 멤버는 이전 문 뒤에 문이 뒤에서 소스 코드의 전체 범위가입니다.  원본 범위의 소스 문에서 디스어셈블리 창에서 코드에 주석을 포함 한 혼합 하는 데 일반적으로 사용 됩니다.  
  
 단순히이 문서의 컨텍스트에 포함 된 코드 문에 대 한 범위를 가져오려면 호출을 [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md) 메서드.  
  
## 참고 항목  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)   
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md)