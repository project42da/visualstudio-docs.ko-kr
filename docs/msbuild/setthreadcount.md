---
title: SetThreadCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
apiname: SetThreadCount
apilocation: filetracker.dll
apitype: COM
helpviewer_keywords: SetThreadCount
ms.assetid: 335335a5-8ca0-4e18-95f5-62aa6a691386
caps.latest.revision: "4"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 7c25dbb399a3be2af9b181c7ccbf495cc03bec19
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="setthreadcount"></a>SetThreadCount
전역 스레드 개수를 설정하고 해당 개수를 현재 스레드에 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT WINAPI SetThreadCount(int threadCount);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `threadCount`  
 사용할 스레드 수입니다.  
  
## <a name="return-value"></a>반환 값  
 스레드 개수가 업데이트된 경우 **SUCCEEDED** 비트가 설정된 **HRESULT**를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** FileTracker.h