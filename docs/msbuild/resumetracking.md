---
title: ResumeTracking | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ResumeTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- ResumeTracking
ms.assetid: d637e019-7c50-4b0a-812e-bc822001e697
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
ms.openlocfilehash: b904d3cb9039088dbaaa3dce8701a32839eb78b9
ms.contentlocale: ko-kr
ms.lasthandoff: 06/03/2017

---
# <a name="resumetracking"></a>ResumeTracking
현재 컨텍스트에서 추적을 다시 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT WINAPI ResumeTracking();  
```  
  
## <a name="return-value"></a>반환 값  
 추적이 다시 시작된 경우 **SUCCEEDED** 비트가 설정된 **HRESULT**를 반환합니다. 컨텍스트를 사용할 수 없어 추적을 다시 시작할 수 없는 경우 **E_FAIL**이 반환됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** FileTracker.h  
  
## <a name="see-also"></a>참고 항목  
 [SuspendTracking](../msbuild/suspendtracking.md)
