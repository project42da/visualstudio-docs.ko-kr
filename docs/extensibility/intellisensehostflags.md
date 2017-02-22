---
title: "IntelliSenseHostFlags | Microsoft Docs"
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
  - "IntellisenseHostFlags"
helpviewer_keywords: 
  - "IntelliSense, IntellisenseHostFlags 열거형"
  - "IntellisenseHostFlags 열거형"
ms.assetid: 0930640b-eb84-48ef-a8f7-d4268f55c99c
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# IntelliSenseHostFlags
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

IntelliSense 호스트 플래그를 지정합니다.  
  
## 구문  
  
```cpp#  
enum IntellisenseHostFlags  
{  
    IHF_READONLYCONTEXT      = 0x00000001  
    IHF_NOSEPARATESUBJECT    = 0x00000002  
    IHF_SINGLELINESUBJECT    = 0x00000004  
    IHF_FORCECOMMITTOCONTEXT = 0x00000008  
    IHF_OVERTYPE             = 0x00000010  
};  
```  
  
#### 매개 변수  
  
|멤버|설명|  
|--------|--------|  
|`IHF_READONLYCONTEXT`|상황에 맞는 버퍼는 읽기 전용입니다.|  
|`IHF_NOSEPARATESUBJECT`|제목 텍스트가 없습니다. 대상 IntelliSense를 포함 하는 상황에 맞는 버퍼 \(의미 `!IHF_READONLYCONTEXT`\).|  
|`IHF_SINGLELINESUBJECT`|제목 텍스트는 다중 명령줄 수 없습니다.|  
|`IHF_FORCECOMMITTOCONTEXT`|`CanCommitIntoReadOnlyBuffer`와 동일합니다.|  
|`IHF_OVERTYPE`|겹쳐쓰기 모드에서 주체 또는 상황에 맞는\) \(에서 편집 해야 합니다.|  
  
## 요구 사항  
 SingleFileeditor.idl  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop>