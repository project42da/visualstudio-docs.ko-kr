---
title: "그래픽 프레임 유효성 검사 | Microsoft Docs"
ms.custom: 
ms.date: 03/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.graphics.FrameValidation
ms.assetid: 1e639182-1301-4e28-9c1e-b5df732f3f1b
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9312ad8a96c5829aae21c87e78a0d5f2f0db1b35
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="graphics-frame-validation"></a>그래픽 프레임 유효성 검사
<!-- VERSIONLESS -->
Visual Studio 2017 및 보다 폭넓게 지원은 **프레임 유효성 검사** 도구입니다.  오류 및 경고 이벤트 목록에 연결 된 유효성 검사 프레임 창에 표시 됩니다.  이 창을 표시 하려면 선택은 **보기 > 프레임 유효성 검사** 메뉴.

![프레임 유효성 검사](media/gfx_diag_frame_validation.png)

클릭는 **유효성 검사 실행** 분석을 시작 하려면 왼쪽된 위 모퉁이에 있는 단추입니다.  프레임의 복잡성에 따라 완료 하는 데 몇 분 정도 걸릴 수 있습니다.  여기에 두 개의 소스에서 조합 표시 되는 데이터: 메시지가 해당 D3D 자체를 내보내는 경우 [SDK 레이어](https://msdn.microsoft.com/library/windows/desktop/ff476881(v=vs.85).aspx) 를 사용 하는 및 도구의 내부 상태 추적에서 수집 되는 데이터입니다. 완료 되 면 데이터의 여러 열을 확인할 수 있습니다.

**열**|**설명**
---|---
이벤트 ID | ID의 항목에 매핑되는 [이벤트 목록](graphics-event-list.md) 창.
심각도 | 손상, 오류, 경고, 정보 또는 메시지입니다.
범주 | 정의 된, 기타 응용 프로그램, 초기화, 정리, 컴파일, 상태 만들기, 상태 설정, 상태를 가져오는, 실행, 리소스 조작, 셰이더를 중복 하 고 사용 하지 않는 합니다.
메시지 | 이벤트와 연결 된 메시지입니다.
이벤트 | 오류 또는 경고와 관련 된 이벤트입니다.

## <a name="see-also"></a>참고 항목  
[그래픽 진단 (DirectX 그래픽 디버그)](visual-studio-graphics-diagnostics.md)   
<!-- /VERSIONLESS -->