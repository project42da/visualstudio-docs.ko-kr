---
title: "방법: 표준 텍스트 표식을 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - standard text markers
ms.assetid: a39fca69-0014-474c-933f-51f0e9b9617e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: bdcdbabae26a9116b1e00910ecef2f83f4075551
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-standard-text-markers"></a>방법: 표준 텍스트 표식을 추가
와 함께 제공 되는 기본 텍스트 표식 유형 중 하나를 만들려면 다음 절차는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 편집기입니다.  
  
### <a name="to-create-a-text-marker"></a>텍스트 마커를 만들려면  
  
1.  하나 또는 두 개의-차원 좌표계, 호출을 사용 중인지 여부에 따라는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> 메서드 또는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> 새 텍스트 마커를 만드는 메서드를 합니다.  
  
     이 메서드 호출에서 마커를 통해 만들 수 있는 텍스트의 범위 표식 유형을 지정 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 인터페이스입니다. 그런 다음이 메서드는 새로 만든된 텍스트 표식에 대 한 포인터를 반환합니다. 표식 유형을에서 수행 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.MARKERTYPE> 열거형입니다. 지정 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 표식 이벤트를 수신 하려면 인터페이스입니다.  
  
    > [!NOTE]
    >  텍스트 표식 주 UI 스레드에서 만듭니다. 코어 편집기 텍스트 표식을 생성 하기 위해 텍스트 버퍼의 내용에는 사용 및 텍스트 버퍼 스레드로부터 안전 하지 않습니다.  
  
## <a name="adding-a-custom-command"></a>사용자 지정 명령 추가  
 구현 된 `IVsTextMarkerClient` 인터페이스에 대 한 포인터를 표식에서 제공 하 고 여러 가지 방법으로 표식 동작을 향상 시킵니다. 첫째, 그러면 사용자 표식에 대 한 팁을 제공 하 고 명령을 실행할 수 있습니다. 이 또한 통해 개별 표식에 대 한 이벤트 알림을 받을 수 마커를 통해 사용자 지정 상황에 맞는 메뉴를 만들 수 있습니다. 마커 상황에 맞는 메뉴에 사용자 지정 명령을 추가 하려면 다음 절차를 따르십시오.  
  
#### <a name="to-add-a-custom-command-to-the-context-menu"></a>상황에 맞는 메뉴에 사용자 지정 명령을 추가 하려면  
  
1.  환경을 호출 하는 상황에 맞는 메뉴 표시 되기 전에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.GetMarkerCommandInfo%2A> 메서드 및 전달 하면 텍스트 표식에 대 한 포인터에 영향을 받는 상황에 맞는 메뉴에서 명령 항목의 수입니다.  
  
     상황에 맞는 메뉴에 있는 중단점 관련 명령을 포함 하는 예를 들어 **중단점 제거** 통해 **새 중단점**다음 스크린샷에 표시 된 대로, 합니다.  
  
     ![마커 상황에 맞는 메뉴](../extensibility/media/vsmarkercontextmenu.gif "vsMarkercontextmenu")  
  
2.  사용자 지정 명령 이름을 식별 하는 일부 텍스트를 다시 전달 합니다. 예를 들어 **중단점 제거** 환경을 제공 하지 않은 이미이 사용자 지정 명령이 될 수 있습니다. 또한 전달 다시 명령 지원 사용 가능 하 고 활성화, 인지 및/또는 온-오프 전환 합니다. 환경이이 정보를 사용 하 여 상황에 맞는 메뉴에서 올바른 방법으로 사용자 지정 명령을 표시 합니다.  
  
3.  환경 명령을 실행 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.ExecMarkerCommand%2A> 메서드를 텍스트 표식 및 상황에 맞는 메뉴에서 선택 된 명령 수에 대 한 포인터를 전달 합니다.  
  
     이 호출에서이 정보를 사용 하 여 텍스트 표식 작업 사용자 지정 명령을 지정을 실행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [텍스트 표식 레거시 API 사용](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [방법: 오류 마커를 구현 합니다.](../extensibility/how-to-implement-error-markers.md)   
 [방법: 사용자 지정 텍스트 표식 만들기](../extensibility/how-to-create-custom-text-markers.md)   
 [방법: 텍스트 표식을 사용 하 여](../extensibility/how-to-use-text-markers.md)