---
title: "IDiaDataSource::openSession | Microsoft Docs"
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
  - "IDiaDataSource::openSession 메서드"
ms.assetid: a3319ed0-3979-483b-9852-c0af96852c48
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaDataSource::openSession
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호를 쿼리 하는 것에 대 한 세션을 엽니다.  
  
## 구문  
  
```cpp#  
HRESULT openSession (   
   IDiaSession** ppSession  
);  
```  
  
#### 매개 변수  
 ppSession  
 \[out\] 반환 된 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 세션 열기를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  다음 표에서 가능한 반환 값을이 메서드에 대 한 표시 됩니다.  
  
|값|설명|  
|-------|--------|  
|E\_UNEXPECTED|[IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md) 개체가 없습니다 이전에 초기화 되었습니다 기호를 소스와.|  
|E\_INVALIDARG|잘못 된 `ppSession` 매개 변수.|  
|E\_OUTOFMEMORY|메모리가 부족 하 여 세션을 열 수 없습니다.|  
  
## 설명  
 열이 메서드는 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 개체는 데이터 소스에 대 한.  
  
 `IDiaSession`개체 데이터 소스에 쿼리를 구현합니다.  세션 디버그 기호는 하나의 주소 공간을 관리합니다.  데이터 원본 심볼에서 설명 된.exe 또는.dll 파일이 있는 경우 \(예를 들어, 여러 프로세스 로드 되어 있기 때문에\) 활성에서 여러 주소 범위를 다음 각 주소 범위에 대 한 세션을 사용 해야 합니다.  
  
## 예제  
  
```cpp#  
IDiaSession* pSession;  
HRESULT hr = pSource->openSession( &pSession );  
if (FAILED(hr))  
{  
   // report error  
}  
```  
  
## 참고 항목  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [개요](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [.Pdb 파일 쿼리](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)