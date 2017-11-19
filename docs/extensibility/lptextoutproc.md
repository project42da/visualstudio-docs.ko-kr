---
title: LPTEXTOUTPROC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LPTEXTOUTPROC
helpviewer_keywords:
- SccMsgDataOnMessage structure
- SccMsgDataOnBeforeGetFile structure
- SccMsgDataIsCancelled structure
- LPTEXTOUTPROC callback function
- SccMsgDataOnAfterGetFile structure
ms.assetid: 2025c969-e3c7-4cf4-a5c5-099d342895ea
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 86c8cce3abf16d7236acdd5ec468b06fdb46f997
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="lptextoutproc"></a>LPTEXTOUTPROC
통합된 개발 환경 (IDE) 내에서 소스 제어 작업을 실행 하는 사용자, 소스 제어 플러그 인 작업에 오류 또는 상태 메시지를 전달 하기 위해 할 수 있습니다. 플러그 인이 목적을 위해 자체 메시지 상자를 표시할 수 있습니다. 그러나 더 원활한 통합에 대 한 플러그 인을 전달할 수 문자열 IDE, 상태 정보를 표시 하는 기본 방법에서 표시 합니다. 이 메커니즘은는 `LPTEXTOUTPROC` 함수 포인터입니다. IDE 오류 및 상태를 표시 하기 위한 (아래에서 자세히 설명)이이 함수를 구현 합니다.  
  
 IDE 소스 제어 플러그 인이 함수에 대 한 함수 포인터 값으로 전달 된 `lpTextOutProc` 호출 될 때 매개 변수는 [SccOpenProject](../extensibility/sccopenproject-function.md)합니다. 예를 들어에 대 한 호출 중에 SCC 작업 중의 [SccGet](../extensibility/sccget-function.md) 많은 파일이 포함 된, 플러그 인 호출할 수는 `LPTEXTOUTPROC` 함수를 주기적으로 표시할 문자열을 전달 합니다. IDE 상태 표시줄, 출력 창 또는 적절 하 게는 별도 메시지 상자에 이러한 문자열을 표시할 수 있습니다. 필요에 따라 IDE 수와 특정 메시지를 표시 하는 **취소** 단추입니다. 이 작업을 취소 하려면 사용자를 통해 및 IDE에 플러그 인이 정보를 전달 하는 기능 제공.  
  
## <a name="signature"></a>서명  
 IDE의 함수에는 다음 서명이 출력:  
  
```cpp  
typedef LONG (*LPTEXTOUTPROC) (  
   LPSTR display_string,  
   LONG mesg_type  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 display_string  
 표시할 텍스트 문자열입니다. 이 문자열 반환 또는 줄 바꿈 캐리지 종료할 수 없습니다.  
  
 mesg_type  
 메시지의 형식입니다. 다음 표에서이 매개 변수에 대해 지원 되는 값을 나열합니다.  
  
|값|설명|  
|-----------|-----------------|  
|`SCC_MSG_INFO, SCC_MSG_WARNING, SCC_MSG_ERROR`|메시지는 정보, 경고 또는 오류 간주 됩니다.|  
|`SCC_MSG_STATUS`|메시지 상태를 표시 하 고 상태 표시줄에 표시할 수 있습니다.|  
|`SCC_MSG_DOCANCEL`|메시지 문자열이 없는 함께 보내집니다.|  
|`SCC_MSG_STARTCANCEL`|시작 표시는 **취소** 단추입니다.|  
|`SCC_MSG_STOPCANCEL`|표시를 중지 한 **취소** 단추입니다.|  
|`SCC_MSG_BACKGROUND_IS_CANCELLED`|백그라운드 작업을 취소할 수는 경우 IDE 요청: IDE 반환 `SCC_MSG_RTN_CANCEL` 작업이 취소 되었으면; 그렇지 않으면 반환 `SCC_MSG_RTN_OK`합니다. `display_string` 로 캐스팅 됩니다 매개 변수는 [SccMsgDataIsCancelled](#LinkSccMsgDataIsCancelled) 소스 제어 플러그 인에서 제공 하는 구조입니다.|  
|`SCC_MSG_BACKGROUND_ON_BEFORE_GET_FILE`|버전 제어에서 검색 하기 전에 파일에 대 한 IDE를 지시 합니다. `display_string` 로 캐스팅 됩니다 매개 변수는 [SccMsgDataOnBeforeGetFile](#LinkSccMsgDataOnBeforeGetFile) 소스 제어 플러그 인에서 제공 하는 구조입니다.|  
|`SCC_MSG_BACKGROUND_ON_AFTER_GET_FILE`|버전 제어에서 검색 한 후 파일에 대 한 IDE를 지시 합니다. `display_string` 로 캐스팅 됩니다 매개 변수는 [SccMsgDataOnAfterGetFile](#LinkSccMsgDataOnAfterGetFile) 소스 제어 플러그 인에서 제공 하는 구조입니다.|  
|`SCC_MSG_BACKGROUND_ON_MESSAGE`|백그라운드 작업의 현재 상태 ide을 선택 합니다. `display_string` 로 캐스팅 됩니다 매개 변수는 [SccMsgDataOnMessage](#LinkSccMsgDataOnMessage) 소스 제어 플러그 인에서 제공 하는 구조입니다.|  
  
## <a name="return-value"></a>반환 값  
  
|값|설명|  
|-----------|-----------------|  
|SCC_MSG_RTN_OK|작업이 성공적으로 완료 또는 문자열 표시 되었습니다.|  
|SCC_MSG_RTN_CANCEL|사용자가 작업을 취소 하려고 합니다.|  
  
## <a name="example"></a>예제  
 IDE 호출 가정은 [SccGet](../extensibility/sccget-function.md) 20 개 파일 이름으로 합니다. 소스 제어 플러그 인 파일 가져오기 도중에 작업을 취소 하지 못하게 하려고 했습니다. 각 파일을 가져온 후 호출 `lpTextOutProc`, 각 파일에 상태 정보를 전달 하 고 보내는 `SCC_MSG_DOCANCEL` 에 보고할 상태가 있으면 메시지입니다. 언제 든 지 플러그 인 들어오는지 반환 값이 `SCC_MSG_RTN_CANCEL` IDE에서 취소의 가져오기 작업에 즉시 파일이 더 이상 없습니다 검색 않도록 합니다.  
  
## <a name="structures"></a>구조체  
  
###  <a name="LinkSccMsgDataIsCancelled"></a>SccMsgDataIsCancelled  
  
```cpp  
typedef struct {  
   DWORD dwBackgroundOperationID;  
} SccMsgDataIsCancelled;  
```  
  
 이 구조와 함께 보내집니다는 `SCC_MSG_BACKGROUND_IS_CANCELLED` 메시지입니다. 취소 된 백그라운드 작업의 ID를 통신에 사용 됩니다.  
  
###  <a name="LinkSccMsgDataOnBeforeGetFile"></a>SccMsgDataOnBeforeGetFile  
  
```cpp  
typedef struct {  
   DWORD dwBackgroundOperationID;  
   PCSTR szFile;  
} SccMsgDataOnBeforeGetFile;  
```  
  
 이 구조와 함께 보내집니다는 `SCC_MSG_BACKGROUND_ON_BEFORE_GET_FILE` 메시지입니다. 검색할 파일의 이름과 ID는 검색을 수행 하는 백그라운드 작업의 통신에 사용 됩니다.  
  
###  <a name="LinkSccMsgDataOnAfterGetFile"></a>SccMsgDataOnAfterGetFile  
  
```cpp  
typedef struct {  
   DWORD dwBackgroundOperationID;  
   PCSTR szFile;  
   SCCRTN sResult;  
} SccMsgDataOnAfterGetFile;  
```  
  
 이 구조와 함께 보내집니다는 `SCC_MSG_BACKGROUND_ON_AFTER_GET_FILE` 메시지입니다. 으로 지정된 된 파일을 검색 하 여 수행한 백그라운드 작업의 ID를 검색 하는 결과 통신에 사용 됩니다. 반환 값에 대 한 참조는 [SccGet](../extensibility/sccget-function.md) 에 어떤 결과적으로 제공 될 수 있습니다.  
  
###  <a name="LinkSccMsgDataOnMessage"></a>SccMsgDataOnMessage  
 [C++]  
  
```  
typedef struct {  
   DWORD dwBackgroundOperationID;  
   PCSTR szMessage;  
   BOOL bIsError;  
} SccMsgDataOnMessage;  
```  
  
 이 구조와 함께 보내집니다는 `SCC_MSG_BACKGROUND_ON_MESSAGE` 메시지입니다. 백그라운드 작업의 현재 상태를 통신에 사용 됩니다. 상태는 IDE에서 표시 하는 문자열로 표현 됩니다 및 `bIsError` 메시지의 심각도 나타냅니다 (`TRUE` 에서 오류 메시지; `FALSE` 의 경고 또는 정보 메시지에 대 한). 상태를 보내기 백그라운드 작업의 ID도 제공 됩니다.  
  
## <a name="code-example"></a>코드 예제  
 여기은 호출의 간단한 예 `LPTEXTOUTPROC` 보내려고는 `SCC_MSG_BACKGROUND_ON_MESSAGE` 호출에 대 한 구조를 캐스팅 하는 방법을 보여 주는 메시지입니다.  
  
```cpp  
LONG SendStatusMessage(  
    LPTEXTOUTPROC pTextOutProc,  
    DWORD         dwBackgroundID,  
    LPCTSTR       pStatusMsg,  
    BOOL          bIsError)  
{  
    SccMsgDataOnMessage msgData = { 0 };  
    LONG                result  = 0;  
  
    msgData.dwBackgroundOperationID = dwBackgroundID;  
    msgData.szMessage               = pStatusMsg;  
    msgData.bIsError                = bIsError;  
  
    result = pTextOutProc(reinterpret_cast<LPCTSTR>(&msgData), SCC_MSG_BACKGROUND_ON_MESSAGE);  
    return result;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDE에 의해 구현 되는 콜백 함수](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)