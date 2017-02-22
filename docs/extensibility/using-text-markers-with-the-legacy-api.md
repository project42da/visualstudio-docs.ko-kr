---
title: "레거시 API와 함께 텍스트 마커를 사용 하 여 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-텍스트 표식"
ms.assetid: 937a0b19-1216-45d5-a7ad-4fe1d6f73097
caps.latest.revision: 16
caps.handback.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 API와 함께 텍스트 마커를 사용 하 여
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트 마커 텍스트 표시에 영향을 줄 수 있는 버퍼를 부동 범위 및 텍스트 영역의 동작입니다.  중단점, 책갈피, 물결 모양 밑줄 및 읽기 전용 영역 표시자를 포함합니다.  텍스트 마커 구문 색상 표시에서 기본적으로 서로 다릅니다.  구문 색상 표시 언어 구문 텍스트 영역과 연결 된 통신 하는 빠른 방법입니다.  구문 색상 표시 속도가 중요 한 경우 Windows 화면을 다시 표시 하면 일반적으로 요청 합니다.  구문 색 텍스트 색을 변경합니다.  텍스트 마커는 다른 텍스트 속성을 변경할 수 있습니다.  텍스트 마커 "부동" 하 고 특별 한 동작을 적용할 수 및 색을 지정 합니다.  
  
 텍스트 표식과 관련 성능 오버 헤드로 인해 많은 마커를 텍스트 버퍼를 만들지 않습니다.  각 마커에 사용자 버퍼 내용을 편집할 때마다 업데이트 됩니다.  
  
> [!NOTE]
>  사용자를 볼 마커 형식 있지만 않은 형태와 스타일을 변경할 수 있습니다.  자세한 내용은 [옵션 대화 상자, 환경, 글꼴 및 색](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)를 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[방법: 표준 텍스트 표식을 추가](../extensibility/how-to-add-standard-text-markers.md)|제공 되는 표준 텍스트 마커 형식을 추가 하는 방법에 설명의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 편집기 텍스트 보기.|  
|[방법: 오류 마커를 구현 합니다.](../extensibility/how-to-implement-error-markers.md)|인스턴스를 구현 하는 방법에 설명의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 빨간색 물결 모양 밑줄을 사용 하 여 오류를 나타내기 위해 사용 되는 표식입니다.|  
|[방법: 사용자 지정 텍스트 표식 만들기](../extensibility/how-to-create-custom-text-markers.md)|텍스트 보기에 사용자 정의 텍스트 마커 형식을 추가 하는 방법에 설명 합니다.|  
|[방법: 텍스트 표식을 사용 하 여](../extensibility/how-to-use-text-markers.md)|텍스트 마커를 추가 하는 방법에 설명 합니다.|  
|[코어 편집기 내](../extensibility/inside-the-core-editor.md)|코어 편집기의 기능 및 코어 편집기를 사용자 지정 하는 방법에 대 한 자세한 정보를 제공 합니다.|  
|[Editor Features](http://msdn.microsoft.com/ko-kr/bdac940d-1f14-4019-a01f-fd0bb3dc7198)|사용할 수 있는 기능에 설명의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 편집기입니다.|  
  
## 참조  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPackageDefinedTextMarkerType>  
 편집기에서 미리 정의 된 또는가 있는 VSPackage 등록 여부 특정 텍스트 표시자 형식에 대 한 정보를 얻기 위한 통일 된 메커니즘을 제공 합니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLineMarker>  
 액세스를 제공 하 고 2 차원 좌표를 사용 하 여 텍스트 마커 텍스트 버퍼에서 위치를 조정 합니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarker>  
 텍스트 마커를 관리 하기 위한 메서드를 제공 합니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient>  
 이 인터페이스에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE 및 텍스트 마커를 조정 하는 데 사용 되는 다른 프로세스입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientAdvanced>  
 기능을 통해 사용할 수 있는 확장은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 추가 콜백을 제공 하는 인터페이스입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientEx>  
 기능을 통해 사용할 수 있는 확장은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 추가 콜백을 제공 하는 인터페이스입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerColorSet>  
 마커 형식을 다른 마커 형식을 동일한 색상 세트를 공유 하는지 여부를 확인할 수 있습니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider>  
 코어 편집기에서 텍스트 표식에 대 한 컨텍스트를 제공합니다.  코어 편집기에 있는 각 텍스트 표식 종류에 대 한 별도 IDE를 만듭니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> 개체입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerGlyphDropHandler>  
 해당 문자 모양을 드래그 앤 드롭 편집 지원 표식에 제공 되는 처리기입니다.  글리프는 표시기의 위치를 나타내는 아이콘입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider>  
 반환 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPackageDefinedTextMarkerType> 인터페이스에서 다른 Vspackages에 마커를 텍스트를 제공 하는 서비스입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStreamMarker>  
 액세스를 제공 하 고 1 차원 좌표를 사용 하 여 텍스트 마커 텍스트 버퍼에서 위치를 조정 합니다.  가능 하면이 인터페이스를 사용 하지 않습니다.