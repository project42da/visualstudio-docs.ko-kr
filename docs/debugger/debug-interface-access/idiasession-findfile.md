---
title: "IDiaSession::findFile | Microsoft Docs"
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
  - "IDiaSession::findFile 메서드"
ms.assetid: a215dc21-b316-40d7-9923-55bfa014976b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSession::findFile
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

컴파일과 이름으로 원본 파일을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT findFile (   
   IDiaSymbol*           pCompiland,  
   LPCOLESTR             name,  
   DWORD                 option,  
   IDiaEnumSourceFiles** ppResult  
);  
```  
  
#### 매개 변수  
 `pCompiland`  
 \[in\] 검색의 컨텍스트로 사용할 컴파일 대상을 나타내는 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 개체입니다.  모든 컴파일에서 소스 파일을 찾으려면 이 매개 변수를 `NULL`로 설정합니다.  
  
 `name`  
 \[in\] 검색할 소스 파일의 이름을 지정합니다.  모든 소스 파일을 검색할 수 있도록 이 매개 변수를 `NULL`로 설정합니다.  
  
 `option`  
 \[in\] 이름 검색에 적용된 비교 옵션을 지정합니다.  [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md) 열거형 값은 단독으로 또는 조합하여 사용할 수 있습니다.  
  
 `ppResult`  
 \[out\] 검색된 소스 파일의 목록을 포함하는 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md) 개체를 반환합니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 오류 코드를 반환합니다.  
  
## 예제  
  
```cpp#  
IDiaEnumSourceFiles* pEnum;  
pSession->findFile( NULL, L"sourcefile.cpp", nsFNameExt, &pEnum );  
```  
  
## 참고 항목  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md)