---
title: "IDiaStackWalkHelper | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaStackWalkHelper2 인터페이스"
ms.assetid: d66e5c84-565d-494e-8486-f91db9a34548
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaStackWalkHelper
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로그램 디버그 데이터베이스 \(.pdb\) 파일을 사용 하 여 스택 워크를 용이 하 게 합니다.  
  
## 구문  
  
```  
  
IDiaStackWalkHelper: IUnknown  
  
```  
  
## 메서드에서 VTable 순서  
 아래 테이블의 메서드를 보여 줍니다. `IDiaStackWalkHelper`:  
  
|메서드|설명|  
|---------|--------|  
|[IDiaStackWalkHelper::get\_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-get-registervalue.md)|레지스터의 값을 검색합니다.|  
|[IDiaStackWalkHelper::put\_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-put-registervalue.md)|레지스터의 값을 설정 합니다.|  
|[IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)|데이터 블록의 메모리에 있는 실행 파일의 이미지를 읽습니다.|  
|[IDiaStackWalkHelper::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddress.md)|지정 된 스택 프레임에 가까운 함수의 반환 주소를 검색합니다.|  
|[IDiaStackWalkHelper::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddressstart.md)|반송 주소 또는 지정 된 스택 주소 근처에 대해 지정 된 스택 프레임을 검색합니다.|  
|[IDiaStackWalkHelper::frameForVA](../../debugger/debug-interface-access/idiastackwalkhelper-frameforva.md)|지정 된 가상 주소를 포함 하는 스택 프레임을 검색 합니다.|  
|[IDiaStackWalkHelper::symbolForVA](../../debugger/debug-interface-access/idiastackwalkhelper-symbolforva.md)|지정 된 가상 주소를 포함 하는 기호를 검색 합니다. **Note:**  기호 형식이 있어야 `SymTagFunctionType` \(값은 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 열거형\).|  
|[IDiaStackWalkHelper::pdataForVA](../../debugger/debug-interface-access/idiastackwalkhelper-pdataforva.md)|지정 된 가상 주소와 관련 된 PDATA 데이터 블록을 반환 합니다.|  
|[IDiaStackWalkHelper::imageForVA](../../debugger/debug-interface-access/idiastackwalkhelper-imageforva.md)|주어진 가상 주소 어딘가에서 실행 파일의 메모리 공간에서 실행 파일을 시작 가상 주소를 검색 합니다.|  
  
## 설명  
 이 인터페이스는 프로그램이 실행 되는 동안 스택 프레임의 목록을 생성 하는 실행 파일에 대 한 정보를 얻을 수 있는 DIA 코드 라고 합니다.  
  
## 호출자에 대 한 참고 사항  
 클라이언트 응용 프로그램이 실행 되는 동안 스택 워크를 지원 하기 위해이 인터페이스를 구현 합니다.  이 인터페이스의 인스턴스로 전달 되는 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) 또는 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md) 방법.  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)   
 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)