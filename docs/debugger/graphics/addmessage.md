---
title: AddMessage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de3460a345dba21e3a8f481adb510b9e3bdd4990
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="addmessage"></a>AddMessage
그래픽 진단에 사용자 지정 메시지를 추가 *HUD* (헤드업 디스플레이).  
  
## <a name="syntax"></a>구문  
  
```C++  
void AddMessage(  
  wchar_t const * szMessage  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szMessage`  
 HUD에 추가할 메시지입니다.  
  
## <a name="remarks"></a>설명  
 그래픽 진단 HUD가 그래픽 진단에서 실행 중인 앱의 왼쪽 위에 표시됩니다. 여기에는 앱 및 그래픽 정보 캡처에 대한 정보, 이 함수를 호출하여 추가되는 메시지가 표시됩니다.  
  
 메시지는 HUD에 추가 하려면 그래픽 정보 캡처 적극적으로 사용할 필요가 없습니다-즉, 인스턴스를 통해 메시지를 추가할 수 있습니다는 `VsgDbg` 클래스 이지만 [Init](init.md) 멤버 함수를 먼저 호출 하지 않습니다. 메시지는 HUD에만 표시되고 그래픽 로그 파일에는 기록되지 않습니다.