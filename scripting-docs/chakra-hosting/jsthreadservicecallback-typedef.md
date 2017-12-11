---
title: JsThreadServiceCallback Typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: dbe67be5-418a-4f66-8b68-b38078a6d140
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c4b7ea4d0d5eaba17269a1777cdf96b5a2a5cda3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsthreadservicecallback-typedef"></a>JsThreadServiceCallback Typedef
스레드 서비스 콜백입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef bool (CALLBACK *JsThreadServiceCallback)(  
   _In_ JsBackgroundWorkItemCallback callback,  
   _In_opt_ void *callbackData  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 callback  
 백그라운드 작업 항목에 대한 콜백입니다.  
  
 callbackData  
 콜백에 전달되는 데이터 인수입니다.  
  
## <a name="remarks"></a>설명  
 호스트는 JsCreateRuntime 호출 시 백그라운드 스레드 서비스를 지정할 수 있습니다. 지정된 경우 백그라운드 작업 항목은 이 콜백을 사용하여 호스트에 전달됩니다. 호스트는 백그라운드 작업 항목 실행을 즉시 시작하고 true를 반환하거나, false를 반환하고 런타임이 스레드에 있는 작업 항목을 처리합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)