---
title: BeginCapture | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9edbb52d-ee0b-4cc4-a382-972bcee067d3
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8774b60f8791373b312437a3e554d17f9582f07f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="begincapture"></a>BeginCapture
와 함께 종료 되는 캡처 간격 시작 `EndCapture`합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
void BeginCapture();  
```  
  
## <a name="remarks"></a>설명  
 캡처 간격은 일반적으로 특정 그리기 호출 종류에 대한 그래픽 정보만 호출하려고 할 때와 같이 한 프레임의 하위 집합을 확장합니다. 캡처 간격이 존재하는 호출을 확장하는 경우 그래픽 정보의 두 프레임이 캡처됩니다. 첫 번째 프레임은 `BeginCapture`에 대한 호출과 존재하는 호출 간에 간격을 확장하고 두 번째 프레임은 존재하는 호출 이후 첫 번째 Direct3D 이벤트와 `EndCapture`에 대한 호출 간의 간격을 확장합니다.  
  
 간격을 캡처하려면 캡처하고 그래픽 정보를 기록 하 여 앱을 준비 해야-호출 즉, 해야 [Init](init.md) 의 인스턴스를 통해는 `VsgDbg` 호출 하기 전에 클래스 `BeginCapture` 또는 `EndCapture`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [EndCapture](endcapture.md)   
 [CaptureCurrentFrame](capturecurrentframe.md)