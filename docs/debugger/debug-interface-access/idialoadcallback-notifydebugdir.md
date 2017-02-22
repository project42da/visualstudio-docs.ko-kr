---
title: "IDiaLoadCallback::NotifyDebugDir | Microsoft Docs"
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
  - "IDiaLoadCallback::NotifyDebugDir 메서드"
ms.assetid: bd04e2f6-0dbf-4742-a556-96f2cd99aa19
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaLoadCallback::NotifyDebugDir
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

.Exe 파일에 디버그 디렉터리를 찾을 수 없는 경우에 호출 됩니다.  
  
## 구문  
  
```cpp#  
HRESULT NotifyDebugDir (   
   BOOL  fExecutable,  
   DWORD cbData,  
   BYTE  data[]  
);  
```  
  
#### 매개 변수  
 `fExecutable`  
 \[in\] `TRUE` 실행 파일이 아닌에서.dbg 파일이 디버그 디렉터리를 읽을 경우.  
  
 `cbData`  
 \[in\] 디버그 디렉터리 데이터의 바이트 수입니다.  
  
 `data[]`  
 \[in\] 디버그 디렉터리에 입력 하는 배열입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 코드는 일반적으로 무시 됩니다.  
  
## 설명  
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드 호출이 콜백을 debug 디렉토리의 실행 파일을 처리 하는 동안 발견 하는 경우.  
  
 이 메서드는 디버그 정보를.pdb 파일에 찾을 수 아닌 다른 지원 해야 할 클라이언트 리버스 실행 파일 및 디버그 파일에 대 한 제거.  이 데이터를 디버그 정보의 유형과 실행 파일 또는.dbg 파일에 있는 클라이언트를 인식할 수 있습니다.  
  
 대부분의 클라이언트이 콜백 하기 때문에 필요 하지 않습니다를 `IDiaDataSource::loadDataForExe` 메서드는 모두.pdb 및.dbg 파일 기호를 사용할 때 투명 하 게 엽니다.  
  
## 참고 항목  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)