---
title: "SCRIPTSTATE 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: SCRIPTSTATE
apilocation: scrobj.dll
helpviewer_keywords: 
  - "SCRIPTSTATE 열거형"
ms.assetid: 5f5deb05-c4bb-4964-8077-e624c6b2a14e
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# SCRIPTSTATE 열거형
스크립팅 엔진의 상태를 지정합니다.  이 열거형을 사용 하 고 있는 [IActiveScript::GetScriptState](../../winscript/reference/iactivescript-getscriptstate.md) , [IActiveScript::SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md) , 및 [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md) 메서드.  
  
## 구문  
  
```  
typedef enum tagSCRIPTSTATE {  
    SCRIPTSTATE_UNINITIALIZED = 0,  
    SCRIPTSTATE_INITIALIZED   = 5,  
    SCRIPTSTATE_STARTED       = 1,  
    SCRIPTSTATE_CONNECTED     = 2,  
    SCRIPTSTATE_DISCONNECTED  = 3,  
    SCRIPTSTATE_CLOSED        = 4  
} SCRIPTSTATE;  
```  
  
## 열거형 값  
  
|||  
|-|-|  
|SCRIPTSTATE\_UNINITIALIZED|스크립트는 방금 만든 되었습니다 있지만 아직 사용 하 여 초기화 되지 않았습니다는 `IPersist*` 인터페이스 및 [IActiveScript::SetScriptSite](../../winscript/reference/iactivescript-setscriptsite.md) .|  
|SCRIPTSTATE\_INITIALIZED|스크립트 초기화 되지 있지만 않습니다 \(다른 개체에 연결 하거나 이벤트 싱크\) 실행 중이거나 임의의 코드를 실행 합니다.  코드 수 수 쿼리 실행에 대 한 호출 하 여는 [IActiveScriptParse::ParseScriptText](../../winscript/reference/iactivescriptparse-parsescripttext.md) 메서드.|  
|SCRIPTSTATE\_STARTED|스크립트 코드를 실행할 수 있습니다 아직으로 추가 된 개체의 이벤트를 싱크 됩니다 없습니다 하지만 [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) 메서드.|  
|SCRIPTSTATE\_CONNECTED|스크립트 로드 되어 이벤트 싱크를 연결 합니다.|  
|SCRIPTSTATE\_DISCONNECTED|스크립트 로드 및 런타임 실행 상태, 있지만 이벤트 싱크에서 일시적으로 연결이 끊어진 됩니다.|  
|SCRIPTSTATE\_CLOSED|스크립트 종료 되었습니다.  스크립트 엔진을 더 이상 작동 하며 대부분의 메서드에 대 한 오류를 반환 합니다.|  
  
## 참고 항목  
 [액티브 스크립트 상수, 열거형 및 오류 코드](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)