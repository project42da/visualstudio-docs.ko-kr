---
title: SetThreadCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SetThreadCount
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SetThreadCount
ms.assetid: 335335a5-8ca0-4e18-95f5-62aa6a691386
caps.latest.revision: 4
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 11a9cee75f912c5fb31cf4a031644abe9c63d744
ms.openlocfilehash: d46fea0afc0d6d47a431954dc80a0b58611de0f3
ms.contentlocale: ko-kr
ms.lasthandoff: 06/03/2017

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
