---
title: '방법: 그래픽 진단 재생 컴퓨터 변경 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 1b9aa3ea-29a0-4e21-bc57-936f33537b5c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 261714c530c2db36b64d7ef07aa19369b3f459bf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-change-the-graphics-diagnostics-playback-machine"></a>방법: 그래픽 진단 재생 컴퓨터 변경
재생할 수 있습니다 그래픽 정보는 원격 컴퓨터 또는 장치를 사용 하 여 또는 로컬 컴퓨터를 사용 하 여 합니다.  
  
## <a name="choosing-a-playback-machine"></a>재생 컴퓨터를 선택합니다.  
 재생 컴퓨터는 컴퓨터 또는 그래픽 로그에서 그래픽 이벤트 재생에 사용 되는 장치입니다. 일반적으로 로컬 컴퓨터는 가장 편리한 옵션 되지만; 캡처를 다른 하드웨어 또는 드라이버 버전은 컴퓨터에 있는 컴퓨터에서 렌더링 문제가 붙은 이 경우 더 잘 문제를 재현 하는 원격 재생 컴퓨터를 선택할 수 있습니다. 있으며 여전히 개발 컴퓨터를 사용 하 여 진단할 수 있습니다.  
  
#### <a name="to-use-the-local-machine-to-play-back-graphics-information"></a>로컬 컴퓨터를 사용 하 여 그래픽 정보 재생 하려면  
  
1.  그래픽 로그 문서 창에서 선택 된 **재생 컴퓨터** 링크 합니다. **원격 디버거 연결** 대화 상자가 나타납니다.  
  
2.  아래 **수동 구성**에 **주소** 속성, 입력 `localhost`합니다.  
  
3.  설정의 **인증 모드** 속성을 **None**합니다.  
  
4.  선택 된 **선택** 단추입니다.  
  
#### <a name="to-use-a-remote-machine-to-play-back-graphics-information"></a>그래픽 정보 재생 하려면 원격 컴퓨터를 사용 하려면  
  
1.  그래픽 로그 문서 창에서 선택 된 **재생 컴퓨터** 링크 합니다. **원격 디버거 연결** 대화 상자가 나타납니다.  
  
2.  아래 **수동 구성**에 **주소** 속성을 Windows 도메인 이름 또는 컴퓨터 또는 장치에 그래픽 정보 재생 하는 데 사용할 IP 주소를 입력 합니다.  
  
3.  재생 컴퓨터에 대 한 연결을 보호 하는 데 사용할 인증 종류를 지정 합니다.  
  
    -   Windows 인증을 위해 설정 된 **인증 모드** 속성을 **Windows**합니다.  
  
    -   인증 안 함 설정는 **인증 모드** 속성을 **None**합니다.  
  
4.  선택 된 **선택** 단추입니다.  
  
> [!NOTE]
>  **원격 디버거 연결** 대화 상자를 된 개발 컴퓨터에 직접 연결 된 파일이 나 동일한 서브넷에 원격 디버깅 대상으로 표시할 수도 있습니다. 그래픽 진단 재생 컴퓨터도 이러한 원격 디버깅 대상 중 하나를 사용 하 여 수동으로 구성 하지 않고 수 있습니다. 에 **원격 디버거 연결** 대화 상자에서 다음을 선택 할 대상 선택 하는 **선택** 단추입니다.  
  
## <a name="see-also"></a>참고 항목  
 [그래픽 로그 문서](graphics-log-document.md)