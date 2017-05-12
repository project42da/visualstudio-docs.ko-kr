---
title: "IActiveScriptAuthor::GetInfoFromContext | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptAuthor.GetInfoFromContext
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptAuthor::GetInfoFromContext"
ms.assetid: 9891b095-6eb5-4473-87c0-c2e5cd2afc1a
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# IActiveScriptAuthor::GetInfoFromContext
반환 코드 블록에는 지정 된 문자에 대 한 앵커 위치 및 정보를 입력합니다.  IntelliSense, 전역 목록 및 매개 변수 팁 구성원에 대 한 정보를 제공합니다.  
  
## 구문  
  
```  
HRESULT GetInfoFromContext(  
   LPCOLESTR  pszCode,  
   ULONG      cchCode,  
   ULONG      ichCurrentPosition,  
   DWORD      dwListTypesRequested,  
   DWORD      *pdwListTypesProvided,  
   ULONG      *pichListAnchorPosition,  
   ULONG      *pichFuncAnchorPosition,  
   MEMBERID   *pmemid,  
   LONG       *piCurrentParameter,  
   IUnknown   **ppunk  
);  
```  
  
#### 매개 변수  
 `pszCode`  
 \[in\] 결과 정보를 생성 하는 데 코드 블록이 문자열의 주소입니다.  
  
 `cchCode`  
 \[in\] 코드 블록의 길이입니다.  
  
 `ichCurrentPosition`  
 \[in\] 블록의 상대적인 시작 문자 위치입니다.  
  
 `dwListTypesRequested`  
 \[in\] 요청 목록 형식입니다.  다음 값 조합이 될 수 있습니다.  
  
|상수|값|설명|  
|--------|-------|--------|  
|SCRIPT\_CMPL\_NOLIST|0x0000|목록이 없습니다.|  
|SCRIPT\_CMPL\_MEMBERLIST|0x0001|멤버 목록입니다.|  
|SCRIPT\_CMPL\_ENUMLIST|0x0002|Enum 목록입니다.|  
|SCRIPT\_CMPL\_PARAMLIST|0x0004|메서드 매개 변수 목록을 호출 합니다.|  
|SCRIPT\_CMPL\_GLOBALLIST|0x0008|전역 목록입니다.|  
  
 SCRIPT\_CMPL\_GLOBALLIST 형식의 다른 완성 항목에 OR 연산자를 사용 하 여 조합할 수 있는 기본 완료 항목으로 처리 됩니다.  스크립트 엔진에 처음 제작 기타 완성 목록 항목에 대 한 형식 정보를 채울 시도 합니다.  실패 하면 엔진 SCRIPT\_CMPL\_GLOBALLIST를 채웁니다.  
  
 `pdwListTypesProvided`  
 \[out\] 제공 하는 목록 유형을 지정 합니다.  
  
 `pichListAnchorPosition`  
 \[out\] 현재 위치에 있는 컨텍스트의 시작 인덱스입니다.  시작 인덱스를 기준으로 블록의 시작입니다.  
  
 이 채워지는 경우에만 `dwListTypesRequested` SCRIPT\_CMPL\_MEMBERLIST, SCRIPT\_CMPL\_ENUMLIST, 또는 SCRIPT\_CMPL\_GLOBALLIST를 포함 합니다.  다른 요청 된 목록 형식에 대 한 결과 정의 되지 않습니다.  
  
 `pichFuncAnchorPosition`  
 \[out\] 현재 위치에 있는 함수 호출의 시작 인덱스입니다.  시작 인덱스를 기준으로 블록의 시작입니다.  
  
 이 때 하 고 현재 위치를 포함 하는 컨텍스트 함수 호출 경우에 채워집니다 `dwListTypesRequested` SCRIPT\_CMPL\_PARAMLIST 포함 되어 있습니다.  그렇지 않으면 결과가 정의 되지 않습니다.  
  
 `pmemid`  
 \[out\] MEMBERID 형식에 의해 정의 된 함수는 `IProvideMultipleClassInfo``ppunk` out 매개 변수입니다.  
  
 이 채워지는 경우에만 `dwListTypesRequested` SCRIPT\_CMPL\_PARAMLIST 포함 되어 있습니다.  
  
 `piCurrentParameter`  
 \[out\] 현재 위치에 있는 매개 변수의 인덱스입니다.  현재 위치에서 함수 이름을 이면\-1이 반환 됩니다.  
  
 `piCurrentParameter` 값을 채워집니다 경우에만 `dwListTypesRequested` SCRIPT\_CMPL\_PARAMLIST 포함 되어 있습니다.  
  
 `ppunk`  
 형태로 제공 되는 형식 정보를 `IProvideMultipleClassInfo` 개체입니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideMultipleClassInfo>   
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)