---
title: 'Idialoadcallback:: Notifydebugdir | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback::NotifyDebugDir method
ms.assetid: bd04e2f6-0dbf-4742-a556-96f2cd99aa19
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 46621c667967f0b87d197839012e830207cc306a
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idialoadcallbacknotifydebugdir"></a>IDiaLoadCallback::NotifyDebugDir
.Exe 파일에는 디버그 디렉터리가 발견 되었을 때 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT NotifyDebugDir (   
   BOOL  fExecutable,  
   DWORD cbData,  
   BYTE  data[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fExecutable`  
 [in] `TRUE` 실행 파일 (.dbg 파일 아님)에서 디버그 디렉터리를 읽을 경우.  
  
 `cbData`  
 [in] 디버그 디렉터리에 있는 데이터의 바이트 수입니다.  
  
 `data[]`  
 [in] 디버그 디렉터리를 사용 하 여 입력은 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 반환 코드는 일반적으로 무시 됩니다.  
  
## <a name="remarks"></a>설명  
 [idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 실행 파일을 처리 하는 동안 디버그 디렉터리를 발견 하면 메서드는이 콜백을 호출 합니다.  
  
 이 메서드는 디버그 정보가.pdb 파일에는 다른 지원 되는 클라이언트를 리버스 엔지니어링 하는 실행 파일 및/또는 디버그 파일에 대 한 요구를 제거 합니다. 이 데이터와 클라이언트는 디버그 정보의 유형 및 실행 파일 또는.dbg 파일에 상주 하는지 여부를 인식할 수 있습니다.  
  
 대부분의 클라이언트 필요는 없지만이 콜백은 때문에 `IDiaDataSource::loadDataForExe` 메서드는 투명 하 게 기호를 제공 하는 데 필요한 경우.pdb와.dbg 파일을 엽니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)