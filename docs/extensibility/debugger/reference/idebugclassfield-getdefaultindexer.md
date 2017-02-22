---
title: "IDebugClassField::GetDefaultIndexer | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugClassField::GetDefaultIndexer"
helpviewer_keywords: 
  - "IDebugClassField::GetDefaultIndexer 메서드"
ms.assetid: 47ce4f45-3816-4b40-909c-5032d0692d75
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugClassField::GetDefaultIndexer
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

기본 인덱서 이름을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetDefaultIndexer(   
   BSTR* pbstrIndexer  
);  
```  
  
```c#  
int GetDefaultIndexer(  
   out string pbstrIndexer  
);  
```  
  
#### 매개 변수  
 `pbstrIndexer`  
 \[out\] 기본 인덱서 이름을 포함 하는 문자열을 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 또는 없음 기본 인덱서 없으면 S\_FALSE를 반환 합니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 클래스의 기본 인덱서 속성으로 표시 되는 `Default` 속성을 배열에 액세스 합니다.  이 특정 한입니다 [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)].  예를 들어 선언 된 기본 인덱서 [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] 사용 됩니다.  
  
```vb#  
Imports System.Collections;  
  
Public Class Class1  
    Private myList as Hashtable  
  
    Default Public Property Item(ByVal Index As Integer) As Integer  
        Get  
            Return CType(List(Index), Integer)  
        End Get  
        Set(ByVal Value As Integer)  
            List(Index) = Value  
        End Set  
    End Property  
End Class  
  
Function GetItem(Index as Integer) as Integer  
    Dim classList as Class1 = new Class1  
    Dim value as Integer  
  
    ' Access array through default indexer  
    value = classList(2)  
  
    ' Access array through explicit property  
    value = classList.Item(2)  
  
    Return value  
End Function  
```  
  
## 참고 항목  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)