---
title: CaptureCurrentFrame | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fcdeee28077f2c7affd1c4cd1f82d8c8cb29494b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
그래픽 로그 파일에 현재 프레임의 나머지 부분을 캡처합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
void CaptureCurrentFrame();  
```  
  
## <a name="remarks"></a>설명  
 다른 캡처가 현재 진행 중인 경우(예: `BeginCapture` 함수에 의해 시작된 캡처) 해당 캡처를 완료하고 그래픽 로그에 다른 프레임으로 기록합니다. 이후에 즉시 그래픽 진단에서 다른 프레임으로도 기록되는 현재 프레임의 나머지 부분 캡처를 시작합니다. 현재 프레임의 끝은 호출로 표시됩니다.  
  
 프레임을 캡처하려면를 캡처하고 그래픽 정보를 기록 하는 응용 프로그램을 준비 해야-호출 즉, 해야 [Init](init.md) 의 인스턴스를 통해는 `VsgDbg` 호출 하기 전에 클래스 `CaptureCurrentFrame`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [초기화](init.md)   
 [BeginCapture](begincapture.md)