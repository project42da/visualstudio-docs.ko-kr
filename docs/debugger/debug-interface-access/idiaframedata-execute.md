---
title: "IDiaFrameData::execute | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaFrameData::execute 메서드"
ms.assetid: 7a6c7d03-1ff1-4059-bd54-5f407eeebc26
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaFrameData::execute
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

스택 해제를 수행 하 고 스택 워크가 프레임 인터페이스에서 결과 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT execute (   
   IDiaStackWalkFrame* frame  
);  
```  
  
#### 매개 변수  
 `frame`  
 \[in\] [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md) 프레임 레지스터의 상태를 유지 하는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  다음 표에서 가능한 반환 값을이 메서드에 대 한 표시 됩니다.  
  
|값|설명|  
|-------|--------|  
|E\_DIA\_INPROLOG|반면 프롤로그 코드에서 스택 프레임을 실행할 수 없습니다.|  
|E\_DIA\_SYNTAX|구문 분석 오류 프레임 프로그램에서 발생 했습니다.|  
|E\_DIA\_FRAME\_ACCESS|메모리 또는 레지스터 액세스 수 없습니다.|  
|E\_DIA\_VALUE|오류 값 \(예를 들어, 0으로 나누기\)의 수치입니다.|  
  
## 설명  
 이 메서드는 스택 해제를 디버깅 하는 동안 호출 됩니다.  [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md) 개체 레지스터에 대 한 업데이트를 받을 수 및 사용 하는 메서드를 제공 하는 클라이언트 응용 프로그램에서 구현 되는 `execute` 메서드.  
  
## 참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)