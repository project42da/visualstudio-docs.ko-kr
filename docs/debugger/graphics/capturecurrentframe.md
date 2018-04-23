---
title: CaptureCurrentFrame | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 41169494424310427e5a8ae6a0af533bdf4be834
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
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