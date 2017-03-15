---
title: "IDiaStackWalkFrame | Microsoft Docs"
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
  - "IDiaStackWalkFrame 인터페이스"
ms.assetid: 42d82845-d6f6-4846-9ecd-9dd169216077
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaStackWalkFrame
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

스택에서 컨텍스트 간에 호출을 유지은 [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md) 메서드.  
  
## 구문  
  
```  
IDiaStackWalkFrame : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaStackWalkFrame`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaStackWalkFrame::get\_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-get-registervalue.md)|레지스터의 값을 검색합니다.|  
|[IDiaStackWalkFrame::put\_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-put-registervalue.md)|레지스터의 값을 설정 합니다.|  
|[IDiaStackWalkFrame::readMemory](../../debugger/debug-interface-access/idiastackwalkframe-readmemory.md)|이미지에서 메모리를 읽습니다.|  
|[IDiaStackWalkFrame::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddress.md)|지정 된 스택 프레임에 가까운 함수의 반환 주소를 검색합니다.|  
|[IDiaStackWalkFrame::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart.md)|반송 주소 또는 지정한 주소 근처에 대해 지정 된 스택 프레임을 검색합니다.|  
  
## 설명  
 이 인터페이스는 레지스터와 메모리 액세스 읽고 쓰거나 반환 주소를 찾을 수 프로그램 실행 시 사용 됩니다.  
  
## 호출자에 대 한 참고 사항  
 클라이언트 응용 프로그램이이 인터페이스를 구현 하 고 전달 하는 인터페이스의 인스턴스는 [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md) 방법입니다.  이 인터페이스의 동일한 인스턴스가 각 호출 하는 동안 상태 레지스터를 유지 하기 위해 다시 사용 됩니다의 `execute` 메서드가 있습니다.  `execute` 메서드 또한 사용 하 여이 인터페이스 반환 주소를 결정 합니다.  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md)