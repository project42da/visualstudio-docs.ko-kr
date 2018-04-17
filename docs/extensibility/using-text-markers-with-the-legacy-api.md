---
title: 텍스트 표식 레거시 API와 함께 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text markers
ms.assetid: 937a0b19-1216-45d5-a7ad-4fe1d6f73097
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0ebef6593a019b09e7ee00cced56777d8488323f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="using-text-markers-with-the-legacy-api"></a>텍스트 표식 레거시 API 사용
텍스트 표식은 부동 광범위 한 표시에 영향을 줄 수 있는 버퍼에서 텍스트 및 텍스트 영역의 동작입니다. 표식은 중단점, 책갈피, 물결 무늬 밑줄로 및 읽기 전용 영역을 포함 합니다. 텍스트 표식 구문 색 지정 기본적으로 다릅니다. 텍스트의 영역과 관련 된 언어 구문 통신할 구문 색 지정을 사용 합니다. 구문 색 지정은 속도가 중요 한 Windows 화면은 연결 될 때 일반적으로 요청 됩니다. 구문 색 지정 텍스트 색을 변경합니다. 텍스트 표식 다른 여러 텍스트 속성을 변경할 수 있습니다. 텍스트 표식 "부동"를 업데이트 하 고 특별 한 동작을 적용할 수의 색을 지정 합니다.  
  
 텍스트 표식와 관련 된 성능 오버 헤드 때문에 텍스트 버퍼에 대 한 많은 표식을 만들지 마십시오. 각 표식 사용자 버퍼 내용을 편집할 때마다 업데이트 됩니다.  
  
> [!NOTE]
>  사용자 표시 표식 유형을 하지만 하지 셰이프와 스타일의 색을 변경할 수 있습니다. 자세한 내용은 참조 [글꼴 및 색, 환경, 옵션 대화 상자](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)합니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[방법: 표준 텍스트 표식을 추가](../extensibility/how-to-add-standard-text-markers.md)|제공 하는 표준 텍스트 표식 유형을 추가 하는 방법에 설명 된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 텍스트 보기로 코어 편집기입니다.|  
|[방법: 오류 마커를 구현 합니다.](../extensibility/how-to-implement-error-markers.md)|인스턴스를 구현 하는 방법에 설명 된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 빨간색 물결 무늬 밑줄을 사용 하 여 오류를 나타내는 데 사용 되는 표식입니다.|  
|[방법: 사용자 지정 텍스트 표식 만들기](../extensibility/how-to-create-custom-text-markers.md)|만들고 텍스트 보기에 사용자 지정 텍스트 표식 유형을 추가 하는 방법을 설명 합니다.|  
|[방법: 텍스트 표식을 사용 하 여](../extensibility/how-to-use-text-markers.md)|텍스트 표식을 추가 하는 방법에 설명 합니다.|  
|[코어 편집기 내](../extensibility/inside-the-core-editor.md)|핵심 편집기의 기능을 설명 하 고 핵심 편집기 사용자 지정 하는 방법에 대 한 세부 정보를 제공 합니다.|  
|[편집기 기능](http://msdn.microsoft.com/en-us/bdac940d-1f14-4019-a01f-fd0bb3dc7198)|사용할 수 있는 기능에 설명 된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 편집기입니다.|  
  
## <a name="reference"></a>참조  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPackageDefinedTextMarkerType>  
 편집기의 미리 정의 된 또는 vspackage 등록 된 특정 텍스트 표식 유형에 대 한 정보를 가져오기 위한 메커니즘을 제공 합니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLineMarker>  
 에 대 한 액세스를 제공 하 고 2 차원 좌표를 사용 하 여 텍스트 버퍼에서 텍스트 표식의 위치를 조정 합니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarker>  
 텍스트 표식을 관리 하기 위한 메서드를 제공 합니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient>  
 에 대 한 콜백을 제공는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE 및 텍스트 마커를 조정 하는 데 사용 되는 다른 프로세스입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientAdvanced>  
 기능을 통해 사용할 수 있는 확장은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 추가 콜백을 제공 하 여 인터페이스입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientEx>  
 기능을 통해 사용할 수 있는 확장은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 추가 콜백을 제공 하 여 인터페이스입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerColorSet>  
 다른 표식 유형을 색의 동일한 집합을 공유 하는지 여부를 확인 하려면 표식 유형을 사용 하도록 설정 합니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider>  
 핵심 편집기에서 텍스트 표식에 대 한 컨텍스트를 제공합니다. 코어 편집기에 있는 각 텍스트 표식 유형에 대 한 IDE를 별도 만듭니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> 개체입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerGlyphDropHandler>  
 끌어서 놓기 편집 문자 모양이 해당 지원 되는 표식의 제공 되는 처리기입니다. 문자 모양을 표식의 위치를 나타내는 아이콘입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider>  
 반환 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPackageDefinedTextMarkerType> 텍스트를 마커 다른 Vspackage 제공 하는 서비스의 인터페이스입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStreamMarker>  
 에 대 한 액세스를 제공 하 고 1 차원 좌표를 사용 하 여 텍스트 버퍼에서 텍스트 표식의 위치를 조정 합니다. 가능한 경우에이 인터페이스를 사용 하지 마십시오.