---
title: "텍스트 버퍼에 액세스 하는 레거시 API를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - text buffers
ms.assetid: cd6cf4ae-fff5-4e23-b293-7cbafdb8aed2
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: facfc1670bf9d04035beffc47b7124bd5d309a7c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="accessing-the-text-buffer-by-using-the-legacy-api"></a>레거시 API를 사용 하 여 텍스트 버퍼에 액세스
텍스트는 텍스트 스트림 및 파일 유지 관리 담당 합니다. 버퍼를 읽거나 쓰게 다른 형식, 있지만 버퍼와 모든 일반 통신은 유니코드를 사용 하 여 수행 됩니다. 레거시 Api에서 텍스트 버퍼가 1 개 또는 2 차원 좌표계 버퍼에서 문자 위치를 식별 하기 사용할 수 있습니다.  
  
## <a name="one--and-two-dimension-coordinate-systems"></a>1 및 2 차원 좌표 시스템  
 1 차원 좌표 위치 147 같은 버퍼의 첫 번째 문자에서는 문자 위치를 기반으로 합니다. 사용 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream> 버퍼에서 1 차원 위치에 액세스 하는 인터페이스입니다. 2 차원 좌표계 쌍 선과 인덱스를 기반으로 합니다. 예를 들어 43 버퍼의 문자를 5 줄에 있게 됩니다 43 해당 줄의 첫 번째 문자의 오른쪽 다섯 문자. 사용 하 여 버퍼에서 2 차원 위치에 액세스 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> 인터페이스입니다. 둘 다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream> 텍스트 버퍼 개체에 의해 구현 되는 인터페이스가 (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>)를 사용 하 여 서로 액세스할 수 있습니다 `QueryInterface`합니다. 다음 다이어그램에서 이러한 오류 코드 및 다른 주요 인터페이스 보여줍니다 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>합니다.  
  
 ![텍스트 버퍼 개체](../extensibility/media/vstextbuffer.gif "vsTextBuffer")  
텍스트 버퍼 개체  
  
 하지만 텍스트 버퍼에서 작동 하는 좌표계 중 하나를 2 차원 좌표를 사용 하도록 최적화 되어 있습니다. 1 차원 좌표계 성능 오버 헤드를 만들 수 있습니다. 따라서 가능 하면 항상 같은 2 차원 좌표계를 사용 합니다.  
  
 텍스트 버퍼의 두 번째 책임 파일 지 속성입니다. 이 작업을 수행 하기 위해 텍스트 버퍼 개체 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> 및 프로젝트 항목에 대 한 문서 데이터 개체 구성 요소와 다른 환경 구성 요소를 지 속성에 관련 된 역할을 합니다. 자세한 내용은 참조 [열기 및 프로젝트 항목 저장](../extensibility/internals/opening-and-saving-project-items.md)합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [레거시 API를 사용 하 여 보기 설정 변경](../extensibility/changing-view-settings-by-using-the-legacy-api.md)  
 레거시 API를 사용 하 여 보기 설정을 변경 하는 방법에 설명 합니다.  
  
 [전역 설정을 모니터링 하는 텍스트 관리자를 사용 하 여](../extensibility/using-the-text-manager-to-monitor-global-settings.md)  
 전역 설정을 모니터링 하는 텍스트 관리자를 사용 하는 방법에 설명...  
  
## <a name="see-also"></a>참고 항목  
 [코어 편집기 내](../extensibility/inside-the-core-editor.md)