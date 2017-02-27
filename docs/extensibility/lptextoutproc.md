---
title: "LPTEXTOUTPROC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LPTEXTOUTPROC"
helpviewer_keywords: 
  - "SccMsgDataOnMessage 구조"
  - "SccMsgDataOnBeforeGetFile 구조"
  - "SccMsgDataIsCancelled 구조"
  - "LPTEXTOUTPROC 콜백 함수"
  - "SccMsgDataOnAfterGetFile 구조"
ms.assetid: 2025c969-e3c7-4cf4-a5c5-099d342895ea
caps.latest.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 21
---
# LPTEXTOUTPROC
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

사용자는 통합된 개발 환경 \(IDE\) 내에서 소스 제어 작업을 실행할 때 소스 제어 플러그 인 작업에 관련 된 오류 또는 상태 메시지를 전달 하려고 합니다. 플러그 인이 목적을 위해 자체 메시지 상자를 표시할 수 있습니다. 그러나 더 원활 하 게 통합에 대 한 플러그 인을 전달할 수 문자열 IDE에서는 상태 정보를 표시 하는 네이티브 방식의에 표시 합니다. 이 메커니즘은는 `LPTEXTOUTPROC` 함수 포인터입니다. IDE 오류 및 상태를 표시 하기 위한 \(아래에서 자세히 설명\)이이 함수를 구현 합니다.  
  
 IDE는 소스 제어 플러그 인이 함수에 대 한 함수 포인터 값으로 전달 된 `lpTextOutProc` 매개 변수를 호출 하는 경우는 [SccOpenProject](../extensibility/sccopenproject-function.md)합니다. 예를 들어에 대 한 호출 중에 SCC 작업 중는 [SccGet](../extensibility/sccget-function.md) 많은 파일을 포함 하는, 플러그 인 호출할 수는 `LPTEXTOUTPROC` 함수를 주기적으로 표시할 문자열을 전달 합니다. IDE는 출력 창에서 또는 적절 하 게 별도 메시지 상자에는 상태 표시줄에 이러한 문자열을 표시할 수 있습니다. 필요에 따라 IDE를 사용 하 여 특정 메시지를 표시할 수 수는 **취소** 단추입니다. 이 통해 작업을 취소 하는 사용자 및 IDE에 플러그 인이 정보를 전달 하는 기능을 제공 합니다.  
  
## Signature  
 IDE의 함수에는 다음 서명이 출력 합니다.  
  
```cpp#  
typedef LONG (*LPTEXTOUTPROC) ( LPSTR display_string, LONG mesg_type );  
```  
  
## 매개 변수  
 display\_string  
 표시할 텍스트 문자열입니다. 이 문자열 캐리지 반환 또는 줄 바꿈 종료할 수 없습니다.  
  
 mesg\_type  
 메시지의 형식입니다. 다음 표에서이 매개 변수에 대해 지원 되는 값을 나열합니다.  
  
|값|설명|  
|-------|--------|  
|`SCC_MSG_INFO, SCC_MSG_WARNING, SCC_MSG_ERROR`|메시지는 정보, 경고 또는 오류로 간주 됩니다.|  
|`SCC_MSG_STATUS`|메시지 상태를 표시 하 고 상태 표시줄에 표시 될 수 있습니다.|  
|`SCC_MSG_DOCANCEL`|메시지 문자열이 없으면와 함께 보내집니다.|  
|`SCC_MSG_STARTCANCEL`|시작 표시는 **취소** 단추입니다.|  
|`SCC_MSG_STOPCANCEL`|표시를 중지 한 **취소** 단추입니다.|  
|`SCC_MSG_BACKGROUND_IS_CANCELLED`|백그라운드 작업을 취소할 수는 경우 IDE 요청: IDE 반환 `SCC_MSG_RTN_CANCEL` 작업이 취소 되었습니다; 그렇지 않으면 반환 `SCC_MSG_RTN_OK`합니다.`display_string` 매개 변수는로 캐스팅 됩니다는 [SccMsgDataIsCancelled](#LinkSccMsgDataIsCancelled) 소스 제어 플러그 인에서 제공 하는 구조입니다.|  
|`SCC_MSG_BACKGROUND_ON_BEFORE_GET_FILE`|버전 제어에서 검색 하기 전에 파일에 대 한 IDE를 지시 합니다.`display_string` 매개 변수는로 캐스팅 됩니다는 [SccMsgDataOnBeforeGetFile](#LinkSccMsgDataOnBeforeGetFile) 소스 제어 플러그 인에서 제공 하는 구조입니다.|  
|`SCC_MSG_BACKGROUND_ON_AFTER_GET_FILE`|버전 제어에서 검색 한 후에 파일에 대 한 IDE를 지시 합니다.`display_string` 매개 변수는로 캐스팅 됩니다는 [SccMsgDataOnAfterGetFile](#LinkSccMsgDataOnAfterGetFile) 소스 제어 플러그 인에서 제공 하는 구조입니다.|  
|`SCC_MSG_BACKGROUND_ON_MESSAGE`|Ide가 백그라운드 작업의 현재 상태입니다.`display_string` 매개 변수는로 캐스팅 됩니다는 [SccMsgDataOnMessage](#LinkSccMsgDataOnMessage) 소스 제어 플러그 인에서 제공 하는 구조입니다.|  
  
## 반환 값  
  
|값|설명|  
|-------|--------|  
|SCC\_MSG\_RTN\_OK|표시 된 문자열 또는 작업이 성공적으로 완료 되었습니다.|  
|SCC\_MSG\_RTN\_CANCEL|사용자 작업을 취소 하려고 합니다.|  
  
## 예제  
 IDE를 호출 하 여 가정은 [SccGet](../extensibility/sccget-function.md) 20 개 파일 이름을 사용 합니다. 소스 제어 플러그 인 파일 가져오기 도중에 작업을 취소 하지 않도록 하려고 합니다. 각 파일을 받은 후 호출 `lpTextOutProc`, 각 파일에 상태 정보를 전달 하 고 보냅니다는 `SCC_MSG_DOCANCEL` 없는 상태 보고서에 있으면 메시지입니다. 언제 든 지 플러그 인 들어오는지 반환 값이 `SCC_MSG_RTN_CANCEL` IDE에서 취소 가져오기 작업에 즉시 파일이 더 이상 없습니다 검색 않도록 합니다.  
  
## 구조체  
  
###  <a name="LinkSccMsgDataIsCancelled"></a> SccMsgDataIsCancelled  
  
```cpp#  
typedef struct { DWORD dwBackgroundOperationID; } SccMsgDataIsCancelled;  
```  
  
 이 구조는 함께 전송 되는 `SCC_MSG_BACKGROUND_IS_CANCELLED` 메시지입니다. 취소 된 백그라운드 작업의 ID를 통신에 사용 됩니다.  
  
###  <a name="LinkSccMsgDataOnBeforeGetFile"></a> SccMsgDataOnBeforeGetFile  
  
```cpp#  
typedef struct { DWORD dwBackgroundOperationID; PCSTR szFile; } SccMsgDataOnBeforeGetFile;  
```  
  
 이 구조는 함께 전송 되는 `SCC_MSG_BACKGROUND_ON_BEFORE_GET_FILE` 메시지입니다. 검색할 파일의 이름과 ID는 검색을 수행 하는 백그라운드 작업의 통신에 사용 됩니다.  
  
###  <a name="LinkSccMsgDataOnAfterGetFile"></a> SccMsgDataOnAfterGetFile  
  
```cpp#  
typedef struct { DWORD dwBackgroundOperationID; PCSTR szFile; SCCRTN sResult; } SccMsgDataOnAfterGetFile;  
```  
  
 이 구조는 함께 전송 되는 `SCC_MSG_BACKGROUND_ON_AFTER_GET_FILE` 메시지입니다. 으로 지정된 된 파일의 검색을 수행 하는 백그라운드 작업의 ID를 검색 하는 결과 통신 하는 데 사용 됩니다. 반환 값에 대 한 참조는 [SccGet](../extensibility/sccget-function.md) 에 어떤 결과적으로 제공 될 수 있습니다.  
  
###  <a name="LinkSccMsgDataOnMessage"></a> SccMsgDataOnMessage  
 \[C\+\+\]  
  
```  
typedef struct { DWORD dwBackgroundOperationID; PCSTR szMessage; BOOL bIsError; } SccMsgDataOnMessage;  
```  
  
 이 구조는 함께 전송 되는 `SCC_MSG_BACKGROUND_ON_MESSAGE` 메시지입니다. 백그라운드 작업의 현재 상태를 전달 하는 데 사용 됩니다. 상태는 IDE에 의해 표시 되는 문자열 표현 됨 및 `bIsError` 메시지의 심각도 나타냅니다 \(`TRUE` 오류 메시지가;에 대 한 `FALSE` 의 경고 또는 정보 메시지에 대 한\). 상태를 전송 하는 백그라운드 작업의 ID도 제공 됩니다.  
  
## 코드 예제  
 다음은 호출 하는 간단한 예 `LPTEXTOUTPROC` 보내도록는 `SCC_MSG_BACKGROUND_ON_MESSAGE` 호출에 대 한 구조를 캐스팅 하는 방법을 보여 주는 메시지입니다.  
  
```cpp#  
LONG SendStatusMessage( LPTEXTOUTPROC pTextOutProc, DWORD         dwBackgroundID, LPCTSTR       pStatusMsg, BOOL          bIsError) { SccMsgDataOnMessage msgData = { 0 }; LONG                result  = 0; msgData.dwBackgroundOperationID = dwBackgroundID; msgData.szMessage               = pStatusMsg; msgData.bIsError                = bIsError; result = pTextOutProc(reinterpret_cast<LPCTSTR>(&msgData), SCC_MSG_BACKGROUND_ON_MESSAGE); return result; }  
```  
  
## 참고 항목  
 [IDE에 의해 구현 되는 콜백 함수](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)