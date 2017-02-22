---
title: "IDebugDocumentContext2::GetStatementRange | Microsoft Docs"
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
  - "IDebugDocumentContext2::GetStatementRange"
helpviewer_keywords: 
  - "IDebugDocumentContext2::GetStatementRange"
ms.assetid: bc94851a-0ec4-47ea-99c7-0a585e54e726
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDocumentContext2::GetStatementRange
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

파일 범위를 문을 문서 컨텍스트를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetStatementRange(   
   TEXT_POSITION* pBegPosition,  
   TEXT_POSITION* pEndPosition  
);  
```  
  
```c#  
int GetStatementRange(   
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
 문 범위 범위가 문서의 컨텍스트 참조 하는 코드를 멤버는 선입니다.  
  
 소스 코드 \(메모 포함\)의 범위를 구하려면이 문서의 컨텍스트 내에서 호출 하는 [GetSourceRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md) 방법입니다.  
  
## 예제  
 다음 예제에서는 단순에이 메서드를 구현 하는 방법을 보여 줍니다. `CDebugContext` 를 노출 하는 개체는 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 인터페이스입니다.  시작 위치는 null 값이 아닙니다만 하면 끝 위치에 채우는이 예제입니다.  
  
```cpp#  
HRESULT CDebugContext::GetStatementRange(TEXT_POSITION* pBegPosition,  
                                         TEXT_POSITION* pEndPosition)    
{    
   HRESULT hr;    
  
   // Check for a valid beginning position argument pointer.    
   if (pBegPosition)    
   {    
      // Copy the member TEXT_POSITION into the local pBegPosition.    
      memcpy(pBegPosition, &m_pos, sizeof (TEXT_POSITION));    
  
      // Check for a valid ending position argument pointer.   
     if (pEndPosition)    
      {    
         // Copy the member TEXT_POSITION into the local pEndPosition.    
         memcpy(pEndPosition, &m_pos, sizeof (TEXT_POSITION));    
      }    
      hr = S_OK;    
   }    
   else    
   {    
      hr = E_INVALIDARG;    
   }    
  
   return hr;    
}    
```  
  
## 참고 항목  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [GetSourceRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md)   
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md)